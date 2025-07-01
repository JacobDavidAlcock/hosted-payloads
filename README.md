# **Hosted Payloads**

A curated collection of asset-based payloads for penetration testing and security research. This repository provides a simple way to host files on GitHub Pages to test for vulnerabilities like Cross-Site Scripting (XSS) when a web application allows users to specify asset URLs (e.g., for images, avatars, or stylesheets).

### **⚠️ Disclaimer**

This project is for **educational and authorized security testing purposes only**. Using these payloads against systems for which you do not have explicit, written permission is illegal and unethical. The maintainers of this repository are not responsible for any misuse or damage caused by this project. Always act responsibly and within the law.

### **How to Use**

1. **Fork this Repository**: Create your own copy of this repository.
2. **Enable GitHub Pages**: In your forked repository, go to Settings \> Pages. Under the "Build and deployment" section, select main as the branch and / (root) as the folder, then click Save.
3. **Get Your Payload URL**: GitHub will provide you with a URL (e.g., https://\<your-username\>.github.io/hosted-payloads/).
4. **Test the Endpoint**: Use the full URL to a specific payload file (e.g., https://\<your-username\>.github.io/hosted-payloads/xss.svg) in the URL input field of the application you are testing.
5. **Observe the Result**: If the application is vulnerable to the specific payload type, the embedded script should execute, or the intended behavior will be observed.

## **Payloads Collection**

The following table lists the available payloads and the vulnerabilities they are designed to test.

| Payload File      | Description & Vulnerability Tested                                                                                                                                                           | Expected Outcome                                                       |
| :---------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------- |
| xss.html          | A basic HTML file with a \<script\> tag. Tests if the application fetches and renders remote HTML content, leading to standard XSS.                                                          | An alert() box with the message "XSS in HTML\!" appears.               |
| img-onerror.html  | An HTML file containing an \<img\> tag with an invalid src and a malicious onerror event handler. Bypasses filters that block \<script\> but not event handlers.                             | An alert() box with the message "XSS from img onerror\!" appears.      |
| xss.svg           | An SVG file with an onload script. Since browsers treat SVGs as images, this is a very common vector for XSS on file upload or URL endpoints.                                                | An alert() box with the message "XSS in SVG\!" appears.                |
| advanced-xss.svg  | An SVG using a \<foreignObject\> tag to embed and execute an HTML \<script\>. Effective against sanitizers that don't recursively parse the SVG's XML tree.                                  | An alert() box with the message "XSS via SVG foreignObject\!" appears. |
| polyglot.gif      | A file that is both a valid GIF and valid JavaScript. Tests for validation based on magic bytes (GIF89a) while allowing script execution if the Content-Type is not strictly enforced.       | An alert() box with the message "XSS from a polyglot GIF\!" appears.   |
| content-sniff.txt | An HTML file disguised with a .txt extension. Tests if the server lacks a X-Content-Type-Options: nosniff header, allowing the browser to perform MIME sniffing and render the file as HTML. | An alert() box with the message "XSS via content sniffing\!" appears.  |
| xss.xml           | An XML file containing a script. Tests if the application parses and renders XML content in a way that allows script execution.                                                              | An alert() box with the message "XSS in XML\!" appears.                |
| cdata-xss.xml     | An XML file using a CDATA section to hide a script from the XML parser. Tests if the application extracts and renders the CDATA content without sanitization.                                | An alert() box with the message "XSS from XML with CDATA\!" appears.   |

### **Contributing**

Contributions are welcome\! If you have a new payload or an improvement, please feel free to fork the repository and submit a pull request.

1. Fork the project.
2. Create a new branch (git checkout \-b feature/new-payload).
3. Add your new payload file(s).
4. Update the README.md table with the new payload information.
5. Commit your changes (git commit \-m 'Add new payload for XYZ').
6. Push to the branch (git push origin feature/new-payload).
7. Open a Pull Request.

### **License**

This project is licensed under the [MIT License](https://www.google.com/search?q=LICENSE).
