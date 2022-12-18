# vector-northware

This repositry is a custom Template to the [MediaWiki](https://www.mediawiki.org/)-Skin ["Vector" (Legacy-Version)](https://www.mediawiki.org/wiki/Skin:Vector).

## Using this Theme

This Theme is implemented through the MW-Extension [Theme](https://www.mediawiki.org/wiki/Extension:Theme).
To Enable the extension, add the Files to the `extensions/` directory and add `wfLoadExtension( 'Theme' );` to the `LocalSettings.php`.
Also add `$wgDefaultTheme='northware'` to the `LocalSettings.php` to set the Theme of the Vector skin.

### Cnfigure Theme-Extension

To use this Theme, store the Repository-Files to

````
extensions/Theme/vector/vector-northware
````

Then register the Template in the extension's `extension.json`-File under the `ResourceModules` Object with the following code:

````php
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

The Theme is now useable through `$wgDefaultTheme` like described above.

## Files of this Repository

I use Sass for this Project, compiled to CSS-Files through the CLI.

The Files `northware-theme.sass` (or `northware-theme.css`) contain the basic customizations to the Vector-Theme.
In `northware-templates.sass` (or `northware-templates.sass`) I'am styling my custom [MediaWiki-Templates](https://www.mediawiki.org/wiki/Help:Templates).

## SASS-Compiling

To compile the SASS-Files throgh the CLI run the following commands in the Repository-Root:

````console
sass -w .:. // To compile every .sass File in the Root-Derectory that has to be compiled.

sass -w northware-theme.sass:northware-theme.css // To compile only the northware-template.sass
sass -w northware-templates.sass:northware-templates.css // To compile only the northware-template.sass
````
