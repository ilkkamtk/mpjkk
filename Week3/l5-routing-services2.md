# Mediapalvelut ja käyttäjäkokemus, Angular Services


## 3/2017

# Router basics
- When using Angular CLI use --routing option

Route declarations:

_app-routing.module.ts_
```typescript
...
import { ExampleComponent } from './example/example.component';

const routes: Routes = [
  {
    path: 'example',
    component: ExampleComponent
  }
];
  ...
```

- `<router-outlet></router-outlet>` declares the placeholder for routed component tree:

_app.component.html_

```html
<h1>App works!</h1>
<router-outlet></router-outlet>
```

---

# Router - Redirects
- By default matching of URLs is done with _startsWith_ algorithm
- `pathMatch: 'full'` can be used to set the algorithm to full matching
- Redirects can be done with `redirectTo`

_app-routing.module.ts_
```typescript
const routes: Routes = [
  {
    path: '',
    pathMatch: 'full',
    redirectTo: 'example'
  },
  {
    path: 'example',
    component: ExampleComponent
  }
];
```
---

# Router - Navigating
- Two ways to navigate between states:
    - Imperatively from within the components code: `this.router.navigateByUrl('example')` or `this.router.navigate(['example'])`
    - Declaratively from within the template: `<div [routerLink]=['example']>`
- URLs starting with `/` are absolute navigations, others relative
- `../` also works for accessing the "parent" URL

_*.component.ts_
```typescript
export class AppComponent {
  constructor(private router: Router) {
  this.router.navigate(['example']);
  }
}
```

_*.component.html_
```html
<a [routerLink]="['example']">Example</a>
```

### Task 1
1. Create new app with Angular CLI. Add routing and style=scss [options](https://github.com/angular/angular-cli/wiki/new)
2. Create components 'top-bar', 'setup' and 'routes' (these are bus routes, not angular routes)
3. Templates:

  _top-bar.component.html_
   ```
   <nav>
       <ul>
         <li>
             <a>Setup</a>
         </li>
         <li>
             <a>Routes</a>
         </li>
       </ul>
   </nav>
   ```
  _setup.component.html_
   ```
   <h1>This is setup</h1>
   ```
_routes.component.html_
   ```
   <h1>This is routes</h1>
   ``` 
    
4. Read the above info about routing and make the app change states between Setup and Routes by clicking the links in top-bar (=navigation)
 
### Services PT II

1. Create new service 'digitransit' to services folder `ng g s services/digitransit`. Copy/paste the content of `digitransit.service.ts` from previous lab.
2. Copy/paste the content of `routes.component.ts` and `routes.component.html` from previous lab
3. Your task is to make the app work like this:
  - User enters the name of a bus stop in 'setup'
    - Two way data binding with [ngModel](https://blog.thoughtram.io/angular/2016/10/13/two-way-data-binding-in-angular-2.html)
    - [Events](http://learnangular2.com/events/)
  - When the name is set, user is redirected to 'routes' which displays the bus routes of the entered bus stop just like in previous lab
  - Advanced: When user clicks on a route, new browser window is opened which displays the current position of selected route in Google Maps
    - Easy: You can create a marker to a certain location by redirecting to `https://maps.google.fi/maps/place/latitude+longitude`
    - Semi-easy: Embed api: https://developers.google.com/maps/documentation/embed/
    - Preferred: https://angular-maps.com/
      - to get a [Goole Maps key](https://developers.google.com/maps/documentation/javascript/), use gmail account, not Metropolia account
      - [Google Developer Console](https://console.developers.google.com/). Täältä saa haettua API keyt, jos on päässyt unohtumaan.
    
