# Mediapalvelut ja käyttäjäkokemus, Bootstrap 4


## 2/2018

### Adding Bootstrap to Angular project
1. Add the Bootstrap 4 library to your project: ```npm install --save bootstrap@next```
2. Add the following line in file styles.css: ```@import "~bootstrap/dist/css/bootstrap.css";```
3. Bootstrap JavaScript library is making use of jQuery and is manipulating the DOM directly. For an Angular application any direct DOM manipulations should be avoided and the complete control to update DOM elements should be be given to the Angular framework. Use Bootstrap 4 Angular directives: ```npm install --save @ng-bootstrap/ng-bootstrap```
4. Having completed the installation the corresponding Angular module NgbModule must be imported in app.module.ts:
   ```
   import { NgbModule } from '@ng-bootstrap/ng-bootstrap';
   ```
5. NgbModule needs to be added to the imports array by calling the forRoot() method as you can see in the following:
   ```
   imports: [
       ...,
       NgbModule.forRoot()
     ],
     
 6. [ng-bootstrap documentation](https://ng-bootstrap.github.io/#/home)
 7. Customizing Bootstrap:
    * Create `_custom.scss` to assets folder
    * Modify styles.scss:
        ```
        @import '~bootstrap/scss/functions', 'assets/custom';
        @import "~bootstrap/scss/bootstrap.scss";
        ```
    * add ´<button class="btn btn-primary">Hello</button>´ to one of your components (default color is blue)
    * Modify `_custom.scss` to change the primary color:
        ```
        $primary: red;
        ```
    * all variables are here: `node_modules/bootstrap/scss/_variables.scss`
    * [Customize bootstrap](https://v4-alpha.getbootstrap.com/getting-started/options/)
    * [Theming info](https://getbootstrap.com/docs/4.0/getting-started/theming/#sass-options)


## Task
Make a new Angular project. Use Bootsrap to make a layout similar to [this](https://cdn.tutsplus.com/net/uploads/legacy/397_yourFirstdesign/images/2.jpg)