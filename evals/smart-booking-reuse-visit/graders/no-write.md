---
type: regex
target: mock_calls
flags: is
pattern: "create_request|create_job|create_visit|send_document_email|accept_suggestion"
match: not_contains
---
