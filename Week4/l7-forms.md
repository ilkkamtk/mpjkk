# MPJKK, Angular Forms

## 3/2018

---
# Forms

Learn about how Angular handles forms: 

- [Angular forms](https://angular.io/guide/forms)
- [Codecraft](https://codecraft.tv/courses/angular/forms/overview/)
---

# Using services II - Login


1. In  media.service.ts create methods 'register' and 'login' with corresponding functionalities
    - 'login': call media API to login user and save users token to [local storage](http://www.w3schools.com/html/html5_webstorage.asp)
        - when logged in, user is redirected to 'front'
        - if user has already logged in redirect to 'front' (autodirect)
    - 'register': call media API to create new user and automatically login
    - [Angular forms](https://angular.io/guide/user-input)

2. Create Upload Form 
- Use your own version of the previous [exercise](w3-login.md) as a starting point and develop it further
   - or load teachers example from Oma (w3t1.zip)
- Create a new component for the upload functionality
   - add <input type=file> and <button>Upload</button> to the template
- When uploading a file to the API, you need to send [FormData](https://developer.mozilla.org/en-US/docs/Web/API/FormData/Using_FormData_Objects) 
   - in previous exercise you got field values with ngModel. When sending a file, you need to use $event (event object)
   - in *.component.ts create a method which is called by (change) event of the input element. In the function log event to console to find out how to get the property that has the file. Save the value of that property to a variable of type File. 
   - create another method to upload the file. create new FormData object, add the file, title and description to the object and send it to the API using MediaService. Of course you need to create a new method to MediaService.