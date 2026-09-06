# .cb — conversation state

The web app keeps each thread's conversation here, one JSON file per thread in `threads/`, committed after every turn.
Agents cannot read this folder: the reviewer and librarian must never see the conversation, and the app enforces that in its tools.
