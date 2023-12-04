sequenceDiagram
participant browser
participant server

    browser -->> server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server -->> browser: HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "HTML is easy", "date": "2023-1-1" }, ... ]
    deactivate server

    Note right of browser: copy the diagram designed by you since it is the same thing that the browser and server do when starting the page, from now on you will be able to see what I have analyzed. When I enter a new note and click the save button:

    browser -->> server POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server -->>
    new_note file, add a new content and date to the json and restart the notes file again
    server -->> browser: All the previous files are reloaded, but having modified the json using new_note the entry made previously can be displayed.

    I hope the exercise is good
