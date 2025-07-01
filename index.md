# XSS Payloads for Testing

This repository hosts various files to test for Cross-Site Scripting (XSS) and other vulnerabilities that may arise from websites allowing asset uploads via URLs. Use these links to test if an endpoint is vulnerable.

## Payloads

- **[HTML Payload](xss.html)**: A standard HTML file with a `<script>` tag.
- **[HTML `onerror` Payload](img-onerror.html)**: An HTML file that uses an `onerror` event on an image tag to execute a script.
- **[SVG Payload](xss.svg)**: A basic SVG image with an `onload` script, a common vector for file upload XSS.
- **[Advanced SVG Payload](advanced-xss.svg)**: An SVG using a `<foreignObject>` tag to embed and execute HTML script content.
- **[XML Payload](xss.xml)**: An XML file with an embedded script to test how the server processes XML content.
- **[XML CDATA Payload](cdata-xss.xml)**: An XML file using a `CDATA` section to hide a script from parsers.
- **[Polyglot GIF Payload](polyglot.gif)**: A file that is both a valid GIF and JavaScript, testing for content-type and magic byte validation bypasses.
- **[Content Sniffing Payload](content-sniff.txt)**: An HTML file disguised as a `.txt` file to test for MIME-type sniffing vulnerabilities.
