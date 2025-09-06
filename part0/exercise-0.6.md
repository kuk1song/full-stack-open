
sequenceDiagram
    participant user
    participant browser
    participant server

    user->>browser: Fill in the text field and click "Save"
    
    Note right of browser: The browser executes JavaScript code that<br/>prevents the default form submission.

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    Note right of browser: The browser sends the new note as a JSON string.
    server-->>browser: HTTP 201 Created
    deactivate server

    Note right of browser: The browser's JavaScript receives the success status.<br/>It updates the notes list on the page without reloading.
