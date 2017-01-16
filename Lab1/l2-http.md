class: center, middle

# Mediapalvelut ja käyttäjäkokemus, Angular HTTP Client


## 1/2017

### Fetching data with HTTP Client, Task A

1. Create new app with Angular CLI
2. Create new component 'http-test'
3. In the component create a method which fetches 'tsconfig.json' file (in 'src') either with GET or POST
    * Example ```this.http.get('example.json').subscribe((res:Response) => this.someVariable = res.json());```
4. First log the data using ```console.log()```
5. Then print the data using HTML (e.g. p, table etc)
6. Remember to call the method

### Fetching data with HTTP Client, Task B

1. Create another method that fetches data from API of your choice
2. First log the data using ```console.log()```
3. Then print the data using HTML (e.g. table)

### Some help
1. Remember to import the Http class to the component and also inject the Http class to constructor
2. [Http class](https://angular.io/docs/ts/latest/api/http/index/Http-class.html)
3. [Bypass CORS if needed](https://www.thepolyglotdeveloper.com/2014/08/bypass-cors-errors-testing-apis-locally/)