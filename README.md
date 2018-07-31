# Readme [![Build Status](https://travis-ci.org/printdeal/styleguide.svg?branch=master)](https://travis-ci.org/printdeal/styleguide)

## Installation
1. Make sure you have the correct version of node installed as defined in the package.json (7.10.1 for example). Do `node -v` to check your version and upgrade/downgrade accordingly. You can use https://github.com/tj/n or NVM to easily switch node versions.
1. Place the fonts into src/fonts manually. The fonts are not included in this source because they are licensed. See your local documentation and or repositories on where to get them. Failing to do this step will result in compilation errors when running installer.sh.
1. Run `cp tasks/config.json.template tasks/config.json` and add the AWS credentials to the new config, by replacing the **** placeholders with the credentials found in the password manager. Failing to do this step will result into broken icons.
1. Run `./installer.sh`.
1. If you run into permission errors please refer to this document: https://docs.npmjs.com/getting-started/fixing-npm-permissions.


## Generating webfonts
1. (Optional for adding new fonts.) Designer hands off original files (TTF, WOFF, or something else, but hopefully one of these).
1. (Optional for adding new fonts.) Use https://www.fontsquirrel.com/tools/webfont-generator to generate the correct versions of the webfonts, follow these steps:
    - Upload the fonts.
    - Pick expert mode :smile:.
    - Check TTF, WOFF and WOFF2.
    - Choose Arial to match x-height, as Arial is our first fallback font.
1. Add the fonts to the this repo, in the `src/fonts` folder.
1. Make sure the paths to the fonts are generated, by publishing the fonts (`gulp fonts:clean && gulp fonts:rev && gulp fonts:release`).
1. Adjust the font-settings in the theme specific `_settings.scss` file.
1. Make sure the `@font-face` rule is generated: check if the `@webfont mixin` is used for this font.
1. Now you're ready for testing the new font.
