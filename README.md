# vector-northware

This repositry is a custom template to the [MediaWiki](https://www.mediawiki.org/)-Skin ["Vector" (legacy-version)](https://www.mediawiki.org/wiki/Skin:Vector).

## Use this Theme

This theme is implemented through the MW-Extension [Theme](https://www.mediawiki.org/wiki/Extension:Theme).
To enable the extension, add the files to the `extensions/` directory and add `wfLoadExtension( 'Theme' );` to the `LocalSettings.php`.
Also add `$wgDefaultTheme='northware'` to the `LocalSettings.php` to set the default theme of the Vector skin.

### Configure Theme-Extension

To use this theme, store the repository-files to

````
extensions/Theme/vector/vector-northware
````

Then register the template in the extension's `extension.json`-file through `ResourceModules` Object with the following code:

````json
"themeloader.skins.vector.northware": {
   "styles": {
    "vector/vector-northware/northware-theme.css": {
     "media": "screen"
    },
    "vector/vector-northware/northware-templates.css": {
     "media": "screen"
    }
   }
  },
````

The theme is now useable through `$wgDefaultTheme` like described above.

## Files of this repository

I use Sass for this project, compiled to CSS-files through the CLI.

The files `northware-theme.sass` (or `northware-theme.css`) contain the basic customizations to the Vector-theme.
In `northware-templates.sass` (or `northware-templates.sass`) I'am styling my custom [MediaWiki-Templates](https://www.mediawiki.org/wiki/Help:Templates).

## SASS-Compiling

To compile the SASS-files throgh the CLI run the following commands in the repository-root:

````console
sass -w .:. // To compile every .sass file in the root-directory that has to be compiled.

sass -w northware-theme.sass:northware-theme.css // To compile only the northware-template.sass
sass -w northware-templates.sass:northware-templates.css // To compile only the northware-template.sass
````
