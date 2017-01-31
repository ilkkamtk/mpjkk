# Mediapalvelut ja käyttäjäkokemus, SASS and customizing Bootstrap


## 3/2017

## SASS/SCSS
- [SASS Home](http://sass-lang.com/)
- [NMP compiler](https://www.npmjs.com/package/node-sass)
    - Command Line Interface is the important part
- [Compiling SASS with npm](https://medium.com/@brianhan/watch-compile-your-sass-with-npm-9ba2b878415b#.bqtqo5rfa)
- [SASS Tutorial](http://tutorialzine.com/2016/01/learn-sass-in-15-minutes/)

### Task 1 - Play with SASS
1. Clone this repo: https://github.com/ilkkamtk/sass_intro.git to folder of your choise
2. Install dependencies `npm install`
    - if using your own laptop, make sure you have [Node](https://nodejs.org/en/) (LTS version) and if it is Windows, [Git Bash](https://git-scm.com/downloads) installed 
3. Modify `scss/main.scss` so that index.html looks like a proper page.
    - use variables, mixins, nesting etc. to change colors, border-radius, fonts... What ever you want. Take your time, no hurry.
    - to see the changes run `npm run watch-css`
        - this will compile scss to css and create `css/main.css`
        - remember to refresh the browser
4. Upload to shell.metropolia.fi and submit a link to Tuubi
        
## Customizing Bootstrap
- [Customization options](http://v4-alpha.getbootstrap.com/getting-started/options/#content)

    - path to `_custom.scss` is `node_modules/bootstrap/scss`
- [Mixins](https://v4-alpha.getbootstrap.com/layout/grid/#sass-mixins)
- If you don't want to use SASS, you can create your own CSS file which has the same classes as Bootstrap. Of course not all, just those you want to modify.

### Task 2
1. Clone this repo: https://github.com/ilkkamtk/CustomBootstrap.git to folder of your choise
2. Install dependencies `npm install`
3. Start automation: `npm run watch-css`
4. There are two layout images in img folder. Choose one and implement that layout with Bootstrap
    - First do the basic layout by using Bootstrap's grid system.
    - Then add Navbars, buttons etc.
    - Customize the colors, sizes etc to finalize the layout
    - The result does not have to be pixel-perfect. Colors, fonts and content can differ from the layout images. But if something is transparent in the layout (like navbar) then make it transparent also in the result.
5. Upload to shell.metropolia.fi and submit a link to Tuubi

## Adding Bootsrap to angular-cli project
- Install Bootstrap with npm:
    
    ```
    npm install bootstrap@next --save
    ```

- Modify `angular-cli.json`. Add to scripts part:

    ```
    ...
    "scripts": [
            "../node_modules/jquery/dist/jquery.js",
            "../node_modules/tether/dist/js/tether.js",
            "../node_modules/bootstrap/dist/js/bootstrap.js"
          ]
    ...
    ```
    
- Add following to `src/styles.scss`:

    ```
    @import '../node_modules/bootstrap/scss/bootstrap';
    ```

