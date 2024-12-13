::: mermaid
sequenceDiagram
participant user
participant browser
participant server

    user->>browser: Completes note's details and clicks submit

    browser->>browser: Updates the note's data structure

    browser->>browser: Calls redraw() to re-render the data on the modified note

    browser->>browser: Executes SendToServer()

    browser->>server:The browser sends new note's info as a JSON payload to the server
    activate server

    Note right of browser: Updates server note's data structure with the new note (content and date)

    server-->>server: Update note's data-structure by adding the information of the new note ( Content and Date)

    server->>browser: Returns 200 Response - OK
    deactivate server

:::
