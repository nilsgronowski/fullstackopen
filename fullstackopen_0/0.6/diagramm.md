```mermaid
sequenceDiagram
    participant browser
    participant server

    browser-->>server: Get https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser: Response: Http 200 - Delivers file

    browser-->>server: Requesting other files like in the non spa app
    activate server
    server-->>browser: Response: Http 200 - Delivers files

    browser-->>server: Post https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    note right of browser:

    note right of browser:Since the server logic is available on the client, a function gets
    note right of browser:active on the submit of the input element and does the following
    note right of browser:stopping the client from reloading the site
    note right of browser:Gets the value from the input field
    note right of browser:Pushes the note into the DOM as li element
    note right of browser:Clears the inputfield value
    note right of browser:Renders the Ul again
    note right of browser:Calls the sendToServer function doing the Http Post

    activate server
    server-->>browser: Response: Http 201 Created
```
