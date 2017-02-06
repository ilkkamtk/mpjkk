# WBMA, Angular Pipes

## 4/2017

---

# Forms

Learn about Angular pipes: 

- [Pipes](https://angular.io/docs/ts/latest/guide/pipes.html)

### Task:  

1. Use the previous exercise [Week4l7.zip](https://tuubi.metropolia.fi/portal/group/tuubi/etusivu/yleiset-tyokalut/tyotilat?p_p_id=Workspaces_WAR_workspaces&p_p_lifecycle=0&p_p_state=normal&p_p_mode=view&p_p_col_id=column-1&p_p_col_count=1&_Workspaces_WAR_workspaces_tab=documents&_Workspaces_WAR_workspaces_workspaceId=340002468) as a starting point
    - extract the zip into folder of your choice and run `npm install`
1. Add following functionality to 'setup' page:
    - User can look up stop names and codes from Google Maps placed in iframe-element
        - when the stop is clicked Google wants users to view larger map for more info like bus stop's code etc.
        - some help [here](https://developers.google.com/maps/documentation/embed/guide#optional_parameters) and [here](http://stackoverflow.com/questions/38037760/how-to-set-iframe-src-in-angular-2-without-causing-unsafe-value-exception)
        - example url for place: `https://www.google.com/maps/embed/v1/place?key=${this.key}&q=Mannerheimintie`
1. Add following functionality to 'routes' page:
    - When user clicks on a route, location of a bus is shown on map which is also in iframe-element (so not in new browser window)
        - example url for coordinates: `https://www.google.com/maps/embed/v1/place?key=${this.key}&q=${lat},${lon}`
    - Display the `tst` property of ´VP´ object in finnish date and time format
        - VP can be found at showBus-method in routes.component.ts (`resp[Object.keys(resp)[0]].VP`)
        - some help [here](https://angular.io/docs/ts/latest/api/common/index/DatePipe-pipe.html) and [here](http://stackoverflow.com/questions/34904683/how-to-set-locale-in-datepipe-in-angular2/35527407)
        - finnish locale is 'fi-FI'
        - create custom pipe to remove the parenthesis from name of route. Example:  `235N to Kuurintorppa (HSL:2614260)`=>`235N to Kuurintorppa`