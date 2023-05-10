## Mermaid file

```mermaid
  
sequenceDiagram
    participant browser
    participant server

    Note right of browser: The user presses the button to sumbit a POST request method to the server
    browser->>server: Post https://studies.cs.helsinki.fi/exampleapp/new_note --- payload { note: 'Hello World' }
    activate server
    deactivate server

    Note right of browser: Browser now GETs HTML && CSS && JS files from server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: GET main.css
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: GET main.js
    deactivate server

    Note right of browser: Browser fetches JSON while executing the JS file

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    Note right of browser: Browser fetches favicon.ico in the middle of fetching JSON file
    browser->>server: GET https://studies.cs.helsinki.fi/favicon.ico
    server-->>browser: <html><head></head><body><a href="/stats">Course stats</a></body></html>
    activate server
    server-->>browser: [{content: "", date: "2023-05-10T14:19:35.148Z"}, {content: "", date: "2023-05-10T14:20:05.809Z"},…]

    deactivate server

    Note right of browser: Browser executes the callback function that renders the notes
    ```