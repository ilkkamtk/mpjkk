# Mediapalvelut ja käyttäjäkokemus, Angular Services


## 3/2017

# Router basics

Route declarations:

_app.module.ts_
```typescript
...
import { RouterModule } from '@angular/router';

const routeConfig = [
  {
    path: 'example',
    component: ExampleComponent
  }
];

@NgModule({
  ...
  imports: [
    ...
   RouterModule.forRoot(routeConfig),
    ...
  ],
  ...
```

`<router-outlet></router-outlet>` declares the placeholder for routed component tree:

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

_app.module.ts_
```typescript
const routeConfig = [
  {
*   path: '',
*   pathMatch: 'full',
*   redirectTo: 'example'
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
*   this.router.navigate(['example']);
  }
}
```

_*.component.html_
```html
<a [routerLink]="['example']">Example</a>
```

### Task 1
1. Create new app with Angular CLI
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

1. Create new folder 'services' to 'app'-folder
2. Create new service 'digitransit' to services folder `ng g s services/digitransit`. Copy/paste the content of `digitransit.service.ts` from previous lab.
3. Copy/paste the content of `routes.component.ts` and `routes.component.html` from previous lab
4. Your task is to make the app work like this:
  - User enters the name of a bus stop in 'setup'
  - When the name is set, user is redirected to 'routes' which displays the bus routes of the entered bus stop just like in previous lab
  - Advanced: When user clicks on a route, new browser window is opened which displays the current position of selected route in Google Maps
    - You can create a marker to a certain location by redirecting to `https://maps.google.fi/maps/place/latitude+longitude`
