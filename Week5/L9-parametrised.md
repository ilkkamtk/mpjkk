# MPJKK, Parameterised Routes

## 5/2018

---

# Parameterised Routes

### Task: Create a new component to display selected media file 

1. Use the previous [exercise](../Week4.l8-pipes.md) as a starting point and develop it further
1. Create a new component for viewing single media files. Features:
    - get a single file from API
    - depending on file type use `<img>`, `<video>` or `<audio>` to show/play media file
        - <http://www.w3schools.com/tags/tag_video.asp>
        - <http://www.w3schools.com/tags/tag_audio.asp>  
    - show also other data related to the media file:
        - title
        - description
        - user (to get username you need to request [User endpoint](http://media.mw.metropolia.fi/wbma/docs/#api-User-GetUser) using media file's `user_id`)
1. Some help:
    - Sending parameters from template:
        - modify `app.routing.module.ts:
    
            ```TypeScript
            const routes: Routes = [
             { path: 'somepage/:param', component: SomeComponent } 
            ];
            ```
        - modify *.component.html:
            ```html
            <a [routerLink]="'/somepage/' + someVariable">
            ```
    - Sending parameters from component:
        ```typescript
          SomeFunction(param: string) {
            this.router.navigate(['somepage', param]); 
          }
        ```
 
    - Recieve parameters:
        ```typescript
          constructor(
                private route: ActivatedRoute) {
            }
          
          this.route.params.subscribe(params => {
                console.log(params);
          };
        ```