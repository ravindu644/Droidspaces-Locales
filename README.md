# Translation Guide

Thank you for contributing translations to Droidspaces! This guide will help you translate the app into your language.

## What You Need

As a translator, you only need access to these two files:
- `values/strings.xml` - All text strings used in the app
- `values/plurals.xml` - Plural forms (if present)

## Quick Start

### Step 1: Find Your Language Code

You need to know your language's ISO 639-1 code. Common examples:
- English: `en` (default, no directory needed)
- Spanish: `es`
- French: `fr`
- German: `de`
- Japanese: `ja`
- Chinese (Simplified): `zh-rCN`
- Chinese (Traditional): `zh-rTW`
- Arabic: `ar`
- Hindi: `hi`
- Russian: `ru`
- Sinhala: `si`
- Tamil: `ta`

**Where to find language codes:**
- [ISO 639-1 Language Codes](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes), [Link 2](https://www.loc.gov/standards/iso639-2/php/code_list.php)
- [Android Locale Codes](https://developer.android.com/guide/topics/resources/providing-resources#LocaleQualifier)
- For region-specific variants: `{language}-r{REGION}` (e.g., `zh-rCN`, `zh-rTW`)

### Step 2: Create Your Translation Files

1. **Create a directory** named `values-{language_code}`:
   - For Spanish: `values-es`
   - For French: `values-fr`
   - For Japanese: `values-ja`
   - etc.

2. **Copy the English files** into your new directory:
   - Copy `values/strings.xml` → `values-{language_code}/strings.xml`
   - Copy `values/plurals.xml` → `values-{language_code}/plurals.xml` (if it exists)

### Step 3: Translate

Open your copied `strings.xml` file and translate all the text content. Keep everything else exactly the same!

**Example:**
```xml
<!-- English (values/strings.xml) -->
<string name="welcome_title">Welcome to Droidspaces</string>
<string name="get_started">Get Started</string>

<!-- Spanish (values-es/strings.xml) -->
<string name="welcome_title">Bienvenido a Droidspaces</string>
<string name="get_started">Comenzar</string>
```

**Note:** Keep "Droidspaces" untranslated in all languages - it's the project name and should remain as "Droidspaces" everywhere.

### Step 4: Submit Your Translation

Submit your translated files via:
- Create a Pull Request
- Issue with attached files
- Or contact the maintainer directly

## Critical Rules - Read Carefully!

### ✅ DO:

1. **Keep all `name` attributes identical**
   - The `name="..."` part must match exactly between English and your translation
   - Only translate the text content inside the tags

2. **Preserve formatting placeholders**
   - Keep `%1$s`, `%1$d`, `%2$s`, etc. exactly as they are
   - These are replaced by the app with actual values
   - Example:
     ```xml
     <!-- English -->
     <string name="container_status">Container %1$s is %2$s</string>

     <!-- Your translation (correct) -->
     <string name="container_status">Container %1$s ist %2$s</string>

     <!-- WRONG - don't change placeholders! -->
     <string name="container_status">Container %s ist %s</string>
     ```

3. **Use UTF-8 encoding**
   - Ensure your XML file starts with: `<?xml version="1.0" encoding="utf-8"?>`
   - This is required for special characters (accents, non-Latin scripts, etc.)

4. **Translate plurals.xml correctly**
   - If `plurals.xml` exists, translate all `<item>` entries
   - Keep the `quantity` attributes (`one`, `other`, `few`, `many`, etc.)
   - Your language may have different plural rules than English

### ❌ DON'T:

1. **Don't change string names** - The `name="..."` attribute must stay identical
2. **Don't change placeholders** - Keep `%1$s`, `%1$d`, etc. exactly as they are
3. **Don't translate "Droidspaces"** - Keep the project name "Droidspaces" as-is in all translations
4. **Don't remove strings** - Translate all strings, even if some seem unused
5. **Don't add new strings** - Only translate existing ones
6. **Don't change XML structure** - Keep the same format and comments

## File Structure Example

After translation, your files should look like:

```
res/
├── values/              # English (default)
│   ├── strings.xml
│   └── plurals.xml
├── values-es/           # Spanish
│   ├── strings.xml
│   └── plurals.xml
├── values-fr/           # French
│   ├── strings.xml
│   └── plurals.xml
└── values-ja/           # Japanese
    ├── strings.xml
    └── plurals.xml
```

## Translation Tips

1. **Context matters** - Read comments in the XML file for context
2. **Be consistent** - Use the same translation for the same English term throughout
3. **Ask questions** - If something is unclear, ask the maintainer

## Common Issues

### Missing Translations
- If you don't translate a string, the app will show English text (fallback)
- This won't crash the app, but users will see mixed languages

### Special Characters
- Use proper Unicode characters for your language
- Ensure your text editor saves files as UTF-8
- Test that special characters display correctly

### Plural Forms
- Different languages have different plural rules
- English uses: `one` and `other`
- Some languages need: `one`, `few`, `many`, `other`
- Research your language's plural rules and add all necessary forms

## Questions?

If you have questions or need help:
1. Check this guide first
2. Look at existing translations for examples
3. Contact the project maintainer

Thank you for helping make Droidspaces available in more languages! 🌍
