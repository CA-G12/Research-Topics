<div>
    <h1> Web Storage</h1>
</div>

## **What is Local storage ?**

Local storage is a read-only property of the window object, it allows you to store data locally in the user's browser with
no expiration date.

The localStorage is stored in SQLite file in a subfolder in the user's profile. You can reach the localStroge database.
in your computer by using this path in windows **C:\Users\MSI\AppData\Local\Google\Chrome\User Data\Default\Local Storage\leveldb**

- **Read-only** means that you can't write or **reassign** the localStorage but you can change the content of it.

- The limit of the local storage is **5MB** across all major browsers, it may be increased to **10MB** but that is not supported 
  by few browsers and includes only strings.

- LocalStorage has 5 methods, such as **setItem()**,  **getItem()**,  **removeItem()**,  **clear()**, ()**key()**.

## **What is Session storage ?**

Session storage is a read-only property of the window, when you open a particular tab, a new session will be created and assigned to
this particular tab.

- The limit of the session storage is **5MB** across all major browsers.

- SessionStorage has 5 methods, such as **setItem()**,  **getItem()**,  **removeItem()**,  **clear()**.

- It stores the state of the user interface of the web application.

- It is also used to pass data between pages instead of using the URL or the hidden input fields.

---
<br>

## **What is the difference between SessionStorage & LocalStorage ?**

- The localStorage is similar to sessionStorage. However, the main difference between them is that the data in localStorage doesn't expire, while the data in sessionStorage is expired and cleared when the tab or the window is closed.

**localStorage:**

1. LocalStorage is not session-based, it must be deleted via javascript or manually.

2. Since the data stored in the localStorage is permanent, it is not preferable to store any sensitive information there.

3. LocalStorage has no expiration date or doesn't expire when the tab/browser is closed.

**sessionStorage:**

1. SessionStorage is session-based and works per window or tab. This means that data is stored only for the duration of a session, i.e., until the browser (or tab) is closed.

2. Regarding security, Session storage is more secure than local storage and is better if you want to store more sensitive information since it ends once the session ends.

3. SessionStorage expires when the tab/browser is closed.

---
<br>

## **```Demo``` a simple usage sessionStorage**

Light & Dark Mode: we can use the sessionStorage to remember the mode when the page refreshes.

1. sessionStorage.getItem() => will get the mode stored in the sessionStorage.

2. We make 2 functions, one called init to run when the page loads and it will check the stored mode, if the value of mode in the session storage is empty, it will set the default mode. if there is mode, another function called setMode will be invoked to set the mode needed.

---
<br>

**When Do You Need Local Storage?**

Since local storage is persistent, it's your best bet to retain data across user visits. If you want to store site preferences or cache long-term data, local storage is appropriate. You may not want to store more sensitive data using local storage, since it is permanent.

As local and session storage are front-end methods, you may want to avoid using them for server-based functions like user login. You could consider cookies as an alternative in these cases.

**When Do You Need Session Storage?**

If you wish to store data only while a user interacts with your site, then session storage is ideal. This could be for short-term caching or usage data about a specific visit to your site.

Session storage is better for storing more sensitive information since it expires.

---
<br>
<br>

## **Team Member:**

- [Shams Elkhodary](https://github.com/shamskhodary).
- [Basil Alshiekh](https://github.com/Bas-Shiekh).
- [Sami Balousha](https://github.com/sam96B).
- [Nada Ayesh](https://github.com/nadasuhailAyesh12).