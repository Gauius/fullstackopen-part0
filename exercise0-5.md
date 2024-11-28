``` mermaid

sequenceDiagram
    participant User
    participant Browser
    participant Server

    User ->> Browser: https://studies.cs.helsinki.fi/exampleapp/spa
    note right of User: User Navigating the Browser

    Browser ->> Server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate Server

    Server -->> Browser: HTML document
    deactivate Server

    Browser ->> Server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate Server

    Server -->> Browser: The CSS file
    deactivate Server

    Browser ->> Server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate Server;

    Server -->> Browser: The JavaScript file
    deactivate Server

    Browser ->> Server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate Server

    Server-->> Browser: [{ "content": "HTML is easy", "date": "2023-1-1" }, ... ]
    deactivate Server

    note right of Browser: The Browser execute the callback function that renders the note

```
