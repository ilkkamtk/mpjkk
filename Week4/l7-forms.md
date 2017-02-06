class: center, middle

# MPJKK, Angular Forms

## 4/2017

---

# Forms

Learn about how Angular handles forms: 

- [Template driven forms](https://blog.thoughtram.io/angular/2016/03/21/template-driven-forms-in-angular-2.html)
- [Model driven forms](https://scotch.io/tutorials/using-angular-2s-model-driven-forms-with-formgroup-and-formcontrol)

### Task: Create form to save user preferences to Local Storage  

1. Use the previous exercise [Week3l5_advanced.zip](https://tuubi.metropolia.fi/portal/group/tuubi/etusivu/yleiset-tyokalut/tyotilat?p_p_id=Workspaces_WAR_workspaces&p_p_lifecycle=0&p_p_state=normal&p_p_mode=view&p_p_col_id=column-1&p_p_col_count=1&_Workspaces_WAR_workspaces_tab=documents&_Workspaces_WAR_workspaces_workspaceId=340002468) as a starting point
    - extract the zip into folder of your choice and run `npm install`
1. Add following functionality to 'setup' page:
    - User can store favourite stop
    - User can store personal information such as name, home address, phone number
    - When user returns to the site, even after closing the browser, all above mentioned information can be used in 'routes' page
    - All above mentioned information can be erased (sort of logout)
    - Advanced: User can look up stop names and codes from Google Maps placed in iframe-element
1. Add following functionality to 'routes' page:
    - The routes of favourite stop are displayed
    - Personal information is displayed
    
### Some help:
- [Local Storage](http://www.w3schools.com/html/html5_webstorage.asp)
