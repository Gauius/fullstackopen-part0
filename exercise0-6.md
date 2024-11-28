``` mermaid

sequenceDiagram
    participant User
    participant Browser
    participant Server

    User ->> Browser: Type Text and Click Save Button
    note right of User: User add new note
    note right of Browser: Browser submit the new note

    Browser ->> Server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    note left of Server: Server process and save the new note
    activate Server

    Server-->> Browser: {content: "New Notes", date: "2024-11-28T13:53:03.774Z"}
    note left of Server: The Browser update the list without reloading
    deactivate Server

    Browser ->> Browser: Render the new list


```
