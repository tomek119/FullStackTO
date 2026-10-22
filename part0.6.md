
# 0.6: New note in Single page app diagram

```mermaid
sequenceDiagram
    participant browser
    participant server

    Note right of browser: User writes a note and clicks Save

    Note right of browser: JavaScript prevents the default form submission

    Note right of browser: A new note object is created with content and date

    Note right of browser: The note is added to the local array and the list is redrawn

    browser->>server: POST /exampleapp/new_note_spa
    Note right of browser: Request body contains the note as JSON

    activate server
    Note right of server: Server processes and saves the new note
    server-->>browser: HTTP 201 Created
    deactivate server

    Note right of browser: The page stays open without reloading
```