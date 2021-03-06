## What is AXRL

Accessibility Reporting Language (AXRL) is a data format designed to describe accessibility tests for Web pages, Native apps and other software. AXRL is designed to be a flexible and extendable data format. AXRL is designed as a JSON format, although because it is based on semantic web technologies, it could also be expressed in other formats.

**Example 1: A basic web page test**

This example shows the test for example.com, where the test produced 2 results. One of the results is "failed", and the second is "passed".

```json
{
  "@context": "https://axrl.org/context/web-v1.json",
  "@type": "WebPageTest",
  "testSubject": "http://example.com",
  "results": [
    {
      "@type": "TestFailure",
      "impact": "Critical",
      "description": "Web pages must have a title",
      "remediation": "Add a title to the web page",
      "helpUrl": "https://dequeuniversity.com/rules/axe/3.1/document-title",
      "node": {
        "@type": "DOMNode",
        "codeSnippet": "<html>...</html>",
        "selector": "html"
      }
    },
    {
      "@type": "TestSuccess",
      "helpUrl": "https://dequeuniversity.com/rules/axe/3.1/color-contrast",
      "node": {
        "@type": "DOMNode",
        "codeSnippet": "<h1>Welcome</h1>",
        "selector": "h1"
      }
    }
  ]
}
```
