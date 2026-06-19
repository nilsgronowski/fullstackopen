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
    ["

    Since the server logic is available on the client, a function gets <br>
    active on the submit of the input element and does the following: <br>
    *1. stopping the client from reloading the site<br>
    *2. Gets the value from the input field<br>
    *3. Pushes the note into the DOM as li element<br>
    *4. Clears the inputfield value<br>
    *5. Renders the Ul again<br>
    *6. Calls the sendToServer function doing the Http Post
  "]
    activate server
    server-->>browser: Response: Http 201 Created
```
