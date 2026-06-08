# ISO Language Codes Dataset

A clean, normalized, and enriched dataset of **ISO 639-1 (alpha-2)** and **ISO 639-2 (alpha-3)** language codes, complete with native names, writing direction (LTR/RTL), and regional locales (Unicode CLDR).

This dataset is scraped from official sources, parsed, and enriched for quick integration into databases, web forms, and localization frameworks.

---

## 📂 Available Files

You can find the dataset in **JSON**, **CSV**, and **Excel (.xlsx)** formats under three different scopes:

### 1. Combined Master List (`languages-all.*`)
Contains all documented languages (living, extinct, ancient, historical, and constructed).
* **[languages-all.json](languages-all.json)** (202 KB)
* **[languages-all.csv](languages-all.csv)** (19 KB)
* **[languages-all.xlsx](languages-all.xlsx)** (26 KB)

### 2. ISO 639-1 - Only 2-Letter Codes (`languages-alpha_2.*`)
Contains only languages that have a 2-letter code representation (the standard for web localization).
* **[languages-alpha_2.json](languages-alpha_2.json)** (76 KB)
* **[languages-alpha_2.csv](languages-alpha_2.csv)** (7 KB)
* **[languages-alpha_2.xlsx](languages-alpha_2.xlsx)** (13 KB)

### 3. ISO 639-2 - Only 3-Letter Codes (`languages-alpha_3.*`)
Contains only languages that do not have a 2-letter equivalent (minority, historical, regional, or ancient languages).
* **[languages-alpha_3.json](languages-alpha_3.json)** (126 KB)
* **[languages-alpha_3.csv](languages-alpha_3.csv)** (12 KB)
* **[languages-alpha_3.xlsx](languages-alpha_3.xlsx)** (17 KB)

---

## 📊 Data Schema

Each language record in the JSON dataset follows this structured schema:

```json
{
  "alpha_2": "tr",
  "alpha_3": "tur",
  "language_name_english": "Turkish",
  "language_name_native": "Türkçe",
  "language_status": "living",
  "is_living_language": true,
  "direction": "ltr",
  "generated_locales": [
    "tr-TR"
  ],
  "meta": {
    "source": "ISO 639-1 / Library of Congress",
    "source_version": "2026-Edition",
    "extracted_at": "2026-06-08"
  }
}
```

### Field Descriptions

| Field | Type | Description | Example |
| :--- | :--- | :--- | :--- |
| `alpha_2` | `string \| null` | 2-letter ISO 639-1 code (null if not available) | `"en"`, `"tr"` |
| `alpha_3` | `string` | 3-letter ISO 639-2 terminology code | `"eng"`, `"tur"` |
| `language_name_english` | `string` | Official English name | `"Turkish"`, `"English"` |
| `language_name_native` | `string \| null` | Native language name | `"Türkçe"`, `"العربية"` |
| `language_status` | `string` | Vital status (`living`, `extinct`, `ancient`, `historical`, `constructed`) | `"living"` |
| `is_living_language` | `boolean` | `true` if language_status is `"living"`, otherwise `false` | `true` |
| `direction` | `string` | Text writing direction (`"ltr"` or `"rtl"`) | `"ltr"`, `"rtl"` |
| `generated_locales` | `array [string]` | Region locale matches enriched from Unicode CLDR | `["tr-TR"]` |
| `meta` | `object` | Extraction source and timestamp metadata | See schema above |

---

## 🛡️ License

This dataset is open-source and available under the [MIT License](LICENSE).
