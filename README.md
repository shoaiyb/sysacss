<p align="center"><img src="preview.jpg?v=3" /></p>
<h1 align="center">language-sl</h1>
<p align="center">Slovenian translations for WonderCMS (by Robert Isoski)</p>

<br><br>

This plugin adds Slovenian translations to the WonderCMS admin area, based on `https://github.com/StephanStanisic/zlanguage-nl_NL` (experimental version). Plugin author: Stephan Stanisic.

# How to adapt to another language
1. Fork this repository (which is the latest with all included translations): https://github.com/robiso/translation-slovenian/
2. Rename repository to "translation-yourlanguage". (If you need help with renaming a repository: https://help.github.com/en/github/administering-a-repository/renaming-a-repository)
3. Rename translation-slovenian.php to "translation-yourlanguage.php" (replace yourlanguage with your actual language).
4. Make sure the repository name matches with the PHP file mentioned in point 3.
5. Edit the SVG file (picture) directly on GitHub (or choose any other editor): https://github.com/robiso/translation-slovenian/edit/master/language-solid.svg
- on line 78, change "Slovenian" to your language.
6. Rename sl.csv to your country locale (list of country locales https://www.science.co.il/language/Locale-codes.php) and save.
7. Translate the .csv file.
8. Update summary file.
9. Create a pull request to https://github.com/robiso/wondercms-cdn-files to the plugins-list file.

## How to use
1. Login to your WonderCMS website.
2. Click "Settings" and click "Plugins".
3. Find plugin in the list and click "install".


## How this works
The translations are all in the si_SL.csv file. Why in CVS? That's how all
other major CMSes do it, so there must be a good reason for it.

You will see something like this a lot: 

```
SECTION NAME
	"> Some text","> Your translation"
```

The 'parser' skips all lines that are not equal to two values, so SECTION NAME (contains one value) is skipped.
All the pairs are in the `preg_replace` regex format. That's all this does. The prepending of `>` and `> ` makes sure that we only match the contents of a tag.

This way, `> Security` will match in 
```
<a href="#security" aria-controls="security" role="tab" data-toggle="tab" class="nav-link">Security</a>
```
and it won't match in
```
<div class="btn-group w-50"><button type="submit" class="btn btn-success" name="betterSecurity" value="on">ON (warning: may break your website)</button></div>
<div class="btn-group w-50"><button type="submit" class="btn btn-danger" name="betterSecurity" value="off">OFF (reset htaccess to default)</button></div>
```
