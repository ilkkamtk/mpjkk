# Mediapalvelut ja käyttäjäkokemus, Angular Services


## 2/2017

### Services PT I

1. Create new app with Angular CLI
2. Create new folder 'services' to 'app'-folder
3. Create new service 'digitransit' to services folder `ng g s services/digitransit`.  It should fetch data from Digitransit Routing API
    - [Documentation](https://digitransit.fi/en/developers/services-and-apis/1-routing-api/1-getting-started/)
    - base url for Helsinki region: https://api.digitransit.fi/routing/v1/routers/hsl/index/graphql
4. As you read the documentation, you find out that Content-Type must be either “application/graphql” or “application/json”. Tip: "application/graphql" works better, but for that we need to [override request headers](https://angular.io/docs/ts/latest/guide/server-communication.html#!#override-default-request-options).
5. In the digitransit-service create method 'getRoutes'. The method should fetch route names and numbers that go through a certain stop
    - use the curl example from the documentation to practise with the API to get the route names and numbers
    - the method should receive the stop name as a parameter
    - it should return JSON
6. Create new component 'routes'. Inject the DigitransitService in the constructor so you can use it in the component.
7. Call getRoutes method in RoutesComponent. Send the name of some nearby bus stop as the parameter (use Google Maps to get stop names) and use console.log to print data to browsers console.
8. Create HTML list of routes to template of routes-component

### Some help
1. Remember to import the Http class to the component and also inject the Http class to constructor
2. [Http class](https://angular.io/docs/ts/latest/api/http/index/Http-class.html)
3. Bypass CORS if needed
    - [Chrome extension](https://chrome.google.com/webstore/detail/allow-control-allow-origi/nlfbmbojpeacfghkpbjhddihlkkiljbi)    
4. Printing data:
    - using expression `{{ variable }}`
    - iterate repeating data: `*ngFor`
    
### Extra: Play with the Postman
1. [Get Postman](https://www.getpostman.com/) and take a look at [docs & tutorials](https://www.getpostman.com/docs/).
2. Use Postman to fetch the same data as you did with curl in the previous task.
3. Also practise the API(s) you have chosen for your project.
