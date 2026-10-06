## Help improve translations

To help others better understand your language, you can help by translating Luciferin in your language by opening an **Issue** or a **Pull Request** here on GitHub.  
If you are not familiar with GitHub, you can join the [Discord community](https://discord.gg/aXf9jeN) and share your translations there.

It's easy: please download the [English language file](https://github.com/sblantipodi/firefly_luciferin/blob/master/src/main/resources/messagebundle_en.properties).

There are some "words" that don't need translation. For example, in Italian there is no reason to translate words like:  
`download`, `start`, `stop`, `letterbox`, `pillarbox`...  
If a term is normally used unchanged in your language, keep its value unchanged rather than deleting the entry.

It is very simple to translate the file. All the phrases or words are in one row.  
Put long phrases in one row without line breaks. The software will indent the text correctly.

Here is an example of a row that needs translation:

**Before translation:**  
`fxml.save=Save`

**After translation:**  
`fxml.save=Speichern`

As you can see, you need to translate only the part after the `=` and not the part before.

## Preserve formatting and placeholders

- Translate only the value after `=`; keep the property key unchanged.
- Keep placeholders such as `{0}` and `{1}` intact, including their numbering.
- Preserve intended escapes such as `\n` and any markup used in the value.
- Keep each entry on one source line and save using the encoding used by the existing language files.
- Check long labels in both the desktop and web interfaces where the same translation is used.
