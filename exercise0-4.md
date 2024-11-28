``` mermaid

sequenceDiagram
    participant User
    participant Browser
    participant Server

    User ->> Browser: Type Text and Click Save Button
    note right of Browser: Browser captures the new note

    Browser ->> Server: POST https://studies.cs.helsinki.fi/exampleapp/new_note

    note left of Server: The server received and append the new note

    Server -->> Browser: 302 Failed to load. HTTP redirect to


    Browser ->> Server: GET https://studies.cs.helsinki.fi/exampleapp/notes;
    activate Server;

    Server -->> Browser: HTML document
    deactivate Server

    Browser ->> Server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate Server;

    Server -->> Browser: The CSS file
    deactivate Server

    Browser ->> Server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate Server;

    Server -->> Browser: The JavaScript file
    deactivate Server

    Browser ->> Server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate Server

    Server -->> Browser: [{ "content": "I am adding a note", "date": "2024-11-28T11:39:47.825Z" }, ... ]
    deactivate Server

    note right of Browser: The Browser renders the page with the new note

```
