+++
title = "How it works"
weight = 4
description = "How Ctrl+Revise works."
+++

Ctrl+Revise listens for keyboard shortcuts and when pressed grabs the highlighted text and sends it to the AI assistant. The AI assistant uses the selected AI model to answer your questions and puts the response in the clipboard to be pasted elsewhere.

{{< mermaid >}}
sequenceDiagram
participant User
participant AI Assistant
User->>AI Assistant: What year was the first car built?
loop Ollama
AI Assistant->>AI Assistant: Process request with the selected AI model
Note right of AI Assistant: Rational thoughts<br/>prevail...
end
AI Assistant->>User: 1886.
{{< /mermaid >}}


## That's it!
Ctrl+Revise is just an interface into the hard work that is being done by the Ollama and the AI models.
