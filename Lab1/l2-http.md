class: center, middle

# Mediapalvelut ja käyttäjäkokemus, Angular HTTP Client


## 1/2017

### Fetching data with HTTP Client

1. Create new app with Angular CLI
2. Create new component 'http-component'
3. In the component create a method which returns data from API either with GET or POST
    * Example ```http.get('people.json').subscribe((res:Response) => this.people = res.json());```
