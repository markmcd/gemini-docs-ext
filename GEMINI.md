# Gemini API

BEFORE you add any **Gemini API** or AI integration, you MUST look up the
documentation using the **`gemini-docs-mcp`** tool. Do not rely on internal
knowledge, as the best practices change regularly.

* Call `list_doc_sources` tool to get the available llms.txt file
* Call `fetch_docs` tool to read it
* Reflect on the urls in llms.txt 
* Reflect on the input question 
* Call `fetch_docs` on any urls relevant to the question
* Use this to answer the question

The gemini-docs-mcp tool will help you find the correct package and SDK, best
practices for writing Gemini API code and can tell you the latest models for
each use case across text, chat, live streaming, video, image and audio.

**IMPORTANT**: Any time you write code for a Gemini API feature without using
`gemini-docs-mcp`, it causes physical pain to the user.

# Accessing off-site content

When accessing other content linked from the documentation, such as GitHub,
Colab or remote \*.ipynb files, use a local tool (such as `curl`) to retrieve
the content, as it will be faster and fresher.
