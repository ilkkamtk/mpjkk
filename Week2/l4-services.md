# Mediapalvelut ja käyttäjäkokemus, Angular Services


## 2/2018

---

### Services PT I

1. Create new app with Angular CLI
2. Create new folder 'services' to 'app'-folder
3. Create new service 'media' to services folder ```ng g s services/media```
4. In the service create a method 'getAllMedia' which fetches all media files from the [media API](http://media.mw.metropolia.fi/wbma/docs/#api-Media-GetMediaFiles) and returns the data as JSON
    * example: 
    ```javascript
    ...
    getAllMedia() {    
     return ...http.get(...)
    }
    ...
    ```
    * see Week 1 task 2 for help
5. Create new component 'listMedia' 
6. Call 'getAllMedia' on ListMedia component and use ```console.log``` to log the returned data 
    - to call getAllMedia, you need to inject MediaService to constructor. Call it mediaService ```...(private mediaService: MediaService)```
    
7. Create HTML list of images to template of ListMedia-component
    - display image's [thumbnail](http://media.mw.metropolia.fi/wbma/docs/#api-Media-GetFile) version
    - display also image's title and description

---


### Services PT II

1. Create another service to services folder. Call it digitransit It should fetch data from Digitransit Routing API `ng g s services/digitransit`.  It should fetch data from Digitransit Routing API
    - [Documentation](https://digitransit.fi/en/developers/services-and-apis/1-routing-api/1-getting-started/)
    - base url for Helsinki region: https://api.digitransit.fi/routing/v1/routers/hsl/index/graphql
2. As you read the documentation, you find out that Content-Type must be either “application/graphql” or “application/json”. Tip: "application/graphql" works better, but for that we need to [override request headers](https://angular.io/docs/ts/latest/guide/server-communication.html#!#override-default-request-options).
3. In the digitransit-service create method 'getRoutes'. The method should fetch route names and numbers that go through a certain stop
    - use the curl example from the documentation to practise with the API to get the route names and numbers
    - the method should receive the stop name as a parameter
    - it should return JSON
4. Create new component 'routes'. Inject the DigitransitService in the constructor so you can use it in the component.
5. Call getRoutes method in RoutesComponent. Send the name of some nearby bus stop as the parameter (use Google Maps to get stop names) and use console.log to print data to browsers console.
6. Create HTML list of routes to template of routes-component

### Some help

1. [Override request headers](https://angular.io/guide/http#headers)
2. [Bypass CORS if needed](https://www.thepolyglotdeveloper.com/2014/08/bypass-cors-errors-testing-apis-locally/)
3. Printing data:
    - using expression ```{{ variable }}```
    - iterate repeating data: ```*ngFor```
4. Use [split](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split) to change filename extension and add thumbnail size info
    - [Array.map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map) to change values once

    
### Extra: Play with the Postman
1. [Get Postman](https://www.getpostman.com/) and take a look at [docs & tutorials](https://www.getpostman.com/docs/).
2. Use Postman to fetch the same data as you did with curl in the previous task.
3. Also practise the API(s) you have chosen for your project.
