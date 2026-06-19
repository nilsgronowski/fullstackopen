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
    Note right of browser: Since the server logic is available on the client, a function gets active on the submit of the input element and does the following:
    1. stopping the client from reloading the site
    2. Gets the value from the input field
    3. Pushes the note into the DOM as li element
    4. Clears the inputfield value
    5. Renders the Ul again
    6. Calls the sendToServer function doing the Http Post
    activate server
    server-->>browser: Response: Http 201 Created
```
