class: center, middle

# Mediapalvelut ja käyttäjäkokemus, Angular HTTP Client


## 1/2017

## Install Postman Chrome Addon
1. [Download and install Postman](https://chrome.google.com/webstore/detail/postman/fhbjgbiflinjbdggehcddcbncdddomop)
2. [Documentation](https://www.getpostman.com/docs/)

### Fetching data with HTTP Client 1

1. Create new app with Angular CLI
2. Create new component 'http-component'
3. Create new text file 'example.json' and type in some JSON formatted data 
4. In the component create a method which returns data from API either with GET or POST
    * Example ```this.http.get('example.json').subscribe((res:Response) => this.someVariable = res.json());```
5. First log the data using ```console.log()```
6. Then print the data using HTML (e.g. table)
7. Remember to call the method

### Fetching data with HTTP Client 1

1. Create another method that fetches data from API of your choice
2. First log the data using ```console.log()```
3. Then print the data using HTML (e.g. table)

### Some help
1. Remember to import the Http class to the component and also inject the Http class to constructor
2. [Http class](https://angular.io/docs/ts/latest/api/http/index/Http-class.html)
3. [Bypass CORS if needed](https://www.thepolyglotdeveloper.com/2014/08/bypass-cors-errors-testing-apis-locally/)
