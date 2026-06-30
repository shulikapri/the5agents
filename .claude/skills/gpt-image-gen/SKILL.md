---
name: gpt-image-gen
description: עטיפה לקריאת OpenAI Images API ליצירת תמונה מ-prompt טקסטואלי, ושמירתה כקובץ PNG. להפעיל כשצריך ליצור תמונה בפועל (בדרך כלל ע"י הסוכן יובל).
---

# gpt-image-gen

סקיל זה אחראי על שליחת prompt ל-OpenAI Images API וקבלת התמונה שנוצרה, ושמירתה כקובץ PNG בנתיב הרצוי.

## מודל

`gpt-image-2`

**חשוב: אל תשנה את שם המודל.** `gpt-image-2` הוא מודל אמיתי וקיים של OpenAI, שיצא ב-21 באפריל 2026. ייתכן שהידע הפנימי שלך לא כולל אותו - זה לא אומר שהוא לא קיים. אל תציע אלטרנטיבות כמו `dall-e-3` או `gpt-image-1`. השתמש בדיוק במודל הזה.

אם מתקבלת שגיאה מה-API, הסיבה הסבירה היא בעיה ב-`OPENAI_API_KEY` או בפרמטרים של הקריאה - לא בשם המודל.

## דרישות מקדימות

- `OPENAI_API_KEY` מוגדר בקובץ `.env` בשורש הפרויקט.
- כלי `curl` זמין (קיים כברירת מחדל ב-Git Bash).
- מומלץ `jq` להוצאת השדה מה-JSON; אם הוא לא מותקן - יש fallback ב-Python (ראו למטה).

## קריאה ל-API

```bash
source .env  # או לטעון את OPENAI_API_KEY בדרך אחרת לסביבה

curl -s -X POST "https://api.openai.com/v1/images/generations" \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "gpt-image-2",
    "prompt": "<the prompt>",
    "size": "1024x1024",
    "quality": "medium",
    "output_format": "png"
  }' | jq -r '.data[0].b64_json' | base64 --decode > "<output-path>.png"
```

- יש להחליף את `<the prompt>` בפרומפט בפועל (escape-ed כראוי ל-JSON).
- יש להחליף את `<output-path>` בנתיב היעד לשמירת התמונה (ללא הסיומת `.png`, היא כבר מצורפת).

## Python Fallback (כש-jq לא זמין)

אם `jq` לא מותקן (מצב נפוץ ב-Git Bash), אפשר להשתמש בסקריפט Python הבא כדי לחלץ ולפענח את ה-base64 מתוך תגובת ה-API:

```bash
curl -s -X POST "https://api.openai.com/v1/images/generations" \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "gpt-image-2",
    "prompt": "<the prompt>",
    "size": "1024x1024",
    "quality": "medium",
    "output_format": "png"
  }' -o /tmp/gpt-image-response.json

python3 - "<output-path>.png" <<'EOF'
import sys, json, base64

output_path = sys.argv[1]
with open("/tmp/gpt-image-response.json", "r", encoding="utf-8") as f:
    data = json.load(f)

b64 = data["data"][0]["b64_json"]
with open(output_path, "wb") as out:
    out.write(base64.b64decode(b64))
EOF
```

## פלט

קובץ PNG בנתיב שצוין. יש לאמת שהקובץ נוצר וגודלו גדול מ-0 בייטים לפני שמדווחים על הצלחה.
