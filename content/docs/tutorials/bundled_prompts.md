+++
title = "Bundled Prompts"
weight = 2
description = "See how to use the AI Assistant for with the bundled prompt messages."
+++

Ctrl+Revise comes configured with a set of prompts that you can use to get the best possible results. The prompt is selected from the settings  and used by pressing the `Ctrl+Revise` keyboard shortcut (Default is: `Alt+C`).

The following prompts are available:
* **Correct Grammar** - Correct the grammar, including spelling and punctuation
* **Make It Friendly** - Give the text a friendly tone
* **Make It Professional** - Give the text a professional tone
* **Make Explanation** - Explain the Text like I am 5
* **Make A Summary** - Create a summary of the text
* **Make Expanded** - Expand on the text, based on if it is fiction or non-fiction
* **Make Headline** - Create a headline based on the text
* **Make It A List** - Create an itemized list based on the text

The prompt messages can be found in the codebase at [ollama.go#L89](https://github.com/bahelit/ctrl_plus_revise/blob/6af175737e6d43cb6065520812401190c637d59a/internal/ollama/ollama.go#L89)

{{< tip >}}
Cycle through the prompts by pressing the `Alt+P` keyboard shortcut.
{{< /tip >}}

{{< tip >}}
You can highlight entire web pages, documents, or text, if the screen isn't writeable the response will be in the clipboard.
{{< /tip >}}
