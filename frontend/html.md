Common Questions

1. A next generation bidirectional communication technology for web application is:
   A/. Web Sockets is a next-generation bidirectional communication technology for web applications that operates over a single socket and is exposed via a JavaScript interface in HTML 5
2. Explain the differences between local storage, session storage, and cookies in HTML5. When would you use each?

Cookies:
Cookies are small pieces of data stored in the browser. They are primarily used for persistent data storage.
Cookies are sent with every HTTP request, including images, CSS, JavaScript, etc., which can increase overhead.
They have a limited size (typically around 4KB).

Local Storage:
Local storage provides a way to store key-value pairs in the browser with no expiration date.
I Data stored in local storage persists even after the browser is closed and reopened.
Local storage is ideal for storing application state, user settings, and caching data that should persist across sessions.

Session Storage:
Session storage is similar to local storage but scoped to a particular browser session.
Data stored in session storage is cleared when the browser tab or window is closed.
Session storage is useful for storing temporary data that should only be available during a single browsing session, such as form data or temporary authentication tokens.

3. The HTML DOM getAttribute()
   method returns the value of an element’s attribute.

4. What is a marquee in HTML?
   Marquee is used for scrolling text on a web page. It scrolls the image or text up, down, left, or right automatically. To apply for a marquee, you have to use </marquee> tags

5. How to handle events in HTML?
   Events can be handled using JavaScript, which can be included in the HTML document using the <script> tag. Event listeners can be added to HTML elements using the addEventListener() method

6. What is the difference between link tag <link> and anchor tag <a>?
   The <link> tag links external resources, such as CSS stylesheets, to an HTML document. The <a> tag creates links to other pages or resources within the same document

7. What is the difference between “display: none” and “visibility: hidden” when used as attributes to the HTML element?
   Elements with “display: none” are not visible and do not take up any space on the page, while elements with “visibility: hidden” are not visible but still take up space.

8. What hierarchy do the style sheets follow?
   If a single selector includes three different style definitions, the definition that is closest to the actual tag takes precedence. Inline style takes priority over embedded style sheets, which takes priority over external style sheets.

9. What is semantic HTML?
   Semantic HTML helps to describe the content's meaning in a way that is understandable not only to humans but also to search engines, screen readers, and other assistive technologies.

   Semantic elements are those which describe the particular meaning to the browser and the developer. Elements like <form>, <table>, <article>, <figure>, etc., are semantic elements.

10. What are void elements in HTML?
    HTML elements which do not have closing tags or do not need to be closed are Void elements. For Example <br />, <img />, <hr />, etc.

11. What is the advantage of collapsing white space?
    In HTML, a blank sequence of whitespace characters is treated as a single space character, Because the browser collapses multiple spaces into a single space character and this helps a developer to indent lines of text without worrying about multiple spaces and maintain readability and understandability of HTML codes.

12. Define multipart form data?
    Multipart form data is one of the values of the enctype attribute. It is used to send the file data to the server-side for processing. The other valid values of the enctype attribute are text/plain and application/x-www-form-urlencoded.
    The media type multipart/form-data is the preferred media type for request payloads that contain files, non-ASCII, and binary data.

13. How to optimize website assets loading?
    To optimize website load time we need to optimize its asset loading and for that:

a. CDN hosting - A CDN or content delivery network is geographically distributed servers to help reduce latency.
b. File compression - This is a method that helps to reduce the size of an asset to reduce the data transfer
c. File concatenation - This reduces the number of HTTP calls
d. Minify scripts - This reduces the overall file size of js and CSS files
e. Parallel downloads - Hosting assets in multiple subdomains can help to bypass the download limit of 6 assets per domain of all modern browsers. This can be configured but most general users never modify these settings.
f. Lazy Loading - Instead of loading all the assets at once, the non-critical assets can be loaded on a need basis.

14. What are the different kinds of Doctypes available?
    The three kinds of Doctypes which are available:

- Strict Doctype
- Transitional Doctype
- Frameset Doctype

15. Can we display a web page inside a web page or Is nesting of webpages possible?
    Yes, we can display a web page inside another HTML web page. HTML provides a tag <iframe> using which we can achieve this functionality.

16. How can we club two or more rows or columns into a single row or column in an HTML table?
    HTML provides two table attributes “rowspan” and “colspan” to make a cell span to multiple rows and columns respectively.

17. In how many ways can we position an HTML element? Or what are the permissible values of the position attribute?
    There are mainly 7 values of position attribute that can be used to position an HTML element:

- static: Default value. Here the element is positioned according to the normal flow of the document.
- absolute: Here the element is positioned relative to its parent element. The final position is determined by the values of left, right, top, bottom.
- fixed: This is similar to absolute except here the elements are positioned relative to the <html> element.
- relative: Here the element is positioned according to the normal flow of the document and positioned relative to its original/ normal position.
- initial: This resets the property to its default value.
- inherit: Here the element inherits or takes the property of its parent.

18. When to use scripts in the head and when to use scripts in the body?
    If the scripts contain some event-triggered functions or jquery library then we should use them in the head section. If the script writes the content on the page or is not inside a function then it should be placed inside the body section at the bottom. In short, follow below three points:

- Place library scripts or event scripts in the head section.
- Place normal scripts that do not write anything on the page, in the head section until there is any performance issue.
- Place scripts that render something on the web page at the bottom of the body section.
