## Mermaid file

```mermaid
  
sequenceDiagram
    participant browser
    participant server

    Note right of browser: The user presses the button to sumbit a POST request method to the server
    browser->>server: Post https://studies.cs.helsinki.fi/exampleapp/new_note --- payload note: 'Hello World'
    activate server
    deactivate server


    ```