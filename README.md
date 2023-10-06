# Week1
•	Week 1: Intermediate JavaScript – Introduction to Intermediate JavaScript
 
•	The Introduction of Intermediate JavaScript – Window Events

•	Popup Window – One of the oldest methods to show additional documents to the user.

•	Popup Windows – Are separate windows with its own independent JavaScript environment while it can navigate (URL) and send messages to the opener window. 

•	Intermediate JavaScript – a user may often encounter the need to work with popups and window methods to enhance user interactions and control the behavior of web applications.

•	Popups/window methods can be used for various purposes such as displaying alerts, confirming actions, opening new browser windows or tabs. 

•	‘Popup Blocking – A system that often tries to block popups and the user. Allowing the user to be somewhat protected from unwanted popups. 

•	Window.Open - The syntax to open a popup is: window. Open (url, name, params) 

•	Url: An url to load into the new window.

•	Name: Each window has a window.name. Which allows us to specify which window to use for the popup window. 

•	Params: The configuration string for the new window. It contains settings, delimited by a comma. There must be no spaces in params, for instance: width=200, height=100.

•	Settings for Params;

•	Position:

•	Left/top (numeric) – coordinates of the window top-left corner on the screen. There is a limitation: a new window cannot be positioned offscreen.

•	Width/height (numeric) – width and height of a new window. 

•	Window Features:

•	Menubar (yes/no) – shows or hides the browser menu on the new window.
•	Toolbar (yes/no) – shows or hides the browser navigation bar (back, forward, reload etc) on the new window.
•	Location (yes/no) – shows or hides the URL field in the new window. FF and IE don’t allow to hide it by default.
•	Status (yes/no) – shows or hides the status bar. Again, most browsers force it to show.
•	Resizable (yes/no) – allows to disable the resize for the new window. Not recommended.
•	Scrollbars (yes/no) – allows to disable the scrollbars for the new window. Not recommended.

•	A popup can be opened by the open (url, name, params) call. It returns the reference to the newly opened window.

•	Browsers block open calls from the code outside of user actions. Usually a notification appears, so that a user may allow them.

•	Browsers open a new tab by default, but if size are provided, then it will be a popup window. 

•	Methods of Scrolling and Resizing:

•	Methods to move/resize:

•	Win.MoveBy(x,y):

•	Move the window relative to current position x pixels to the right and y pixels down. Negative values are allowed (to move left/up).

•	Win.MoveTo(x,y):

•	Move the window to coordinates (x,y) on the screen. 

•	Win.ResizeBy(width,height)

•	Resize the window by given width/height relative to the current size. Negative values are allowed. 

•	Win.ResizeTo(width,height):

•	Resize the window.onresize event.

•	Scrolling a Window

•	Scrolling:

•	Window.Scrollx and window.scrollY’:

•	Window.Scrollx represents the horizontal scroll position of the document.

•	Window.ScrollTo(x,y) and window.scrollBy (x,y):

•	Allows you to set the scroll position to specific coordinates (x,y) within the document. 

•	Window.ScrollBy(x,y) allows you to scroll by a specified amount relative to the current scroll position.

•	These methods are helpful for programmatically scrolling to specific sections of your webpage.

•	Element.scrollIntoView() method:

•	This method can be called on an HTML element to scroll the window so that the element becomes visible within the viewport.


•	Useful for creating smooth scrolling navigation or focusing on specific content.
•	Scroll Events (scroll):

•	You can add event listeners to the scroll event on the window object to execute JavaScript code when the user scrolls.


•	Useful for implementing features like "infinite scrolling" or updating elements as they become visible during scrolling.
•	Scroll Behavior (behavior: 'smooth'):

•	When using window.scrollTo() or the Element.scrollIntoView() method, you can set the behavior option to 'smooth' to create a smooth scroll animation.
•	This provides a more visually pleasing scrolling experience for users.

•	Understanding window sizes and scrolling is essential for creating responsive web designs and interactive web applications that adapt to various screen sizes and provide a smooth user experience during scrolling interactions.

•	Focusing: Focus/Blur

•	An element receives the focus when the user either clicks on it or uses the “tab” key on the keyboard.


•	Day 2: Cross-Window Communication
•	The Same Origin (same site) policy limits access of windows and frames to each other. 
•	The concept behind Cross-Window Communication is that if a user has two pages open: one from john-smith.com, and another one is gmail.com, then they wouldn’t want a script from john-smith.com to read our mail from gmail.com. So, the purpose of the “Same Origin” policy is to protect users from information theft. 

•	Same Origin – Two URLs are said to have the “same origin” if they have the same protocol, domain, and port. 

•	These URLs all share the same origin:

•	http://site.com
•	http://site.com/
•	http://site.com/my/page.html

•	These URLs do not share the same origin:
•	http://www.site.com (another domain: www. matters)
•	http://site.org (another domain: .org matters)
•	https://site.com (another protocol: https)
•	http://site.com:8080 (another port: 8080)
•	The “Same Origin” Policy: 
•	If a window or frame (e.g., a popup or frame) is from the same origin (same website, protocol, and port), full access to its content will be allowed.
•	This means that a user can interact with the variables, document, and other resources.
•	If the window or frame comes from a different origin (it might be a different website, protocol, or port) access to its content is restricted. 
•	A user can change the location and redirect the user, but the user cannot read the location or access any other information, preventing information leaking and causing potential security risks.

•	IFRAME: 
•	An “IFrame” tag hosts a separate embedded window, with its own separate document and window objects. 
•	IFRAME can be accessed using properties such as:
•	Iframe.contentWindow to get the window inside the <iframe>.
•	Ifram.contentDocument to get the document inside the <iframe>, 
•	Iframe.contentWindow.document. 

•	Iframe.onload vs iframe.contentWindow.onload:

•	The iframe.onload event (on the <iframe>tag) is essentially the same as iframe.contentWindow.onload (on the embedded window object). It triggers when the embedded window fully loads with all resources. 

•	Windows on Subdomain: Document.Domain:

•	Using the ‘document .domain’ property can relax the Same-Origin Policy for windows on subdomains in a web application. 

•	Same-Origin Policy: Normally, windows on different subdomains are treated as different origins, subject to the Same-Origin Policy, which restricts cross-origin interactions for security reasons. 

•	Subdomains: Subdomains are parts of a website’s domain hierarchy such as:

•	Sub1.example.com’ and Sub2.example.com 

•	Document.domain’Property: By setting the ‘document . domain’ property, can indicate that windows on different subdomains should be treated as if they have the same origin.

•	Usage: This property is set in JavaScript and should be the same for all windows within the same application, but it can be set to a more relaxed shared domain to enable cross-subdomain communication. 

•	Example: If the main domain is example.com, setting document.domain to "example.com" in both sub1.example.com and sub2.example.com will make them share the same origin, allowing them to interact without the Same-Origin Policy restrictions.

•	Security Implications: Be cautious when using document.domain, as it can introduce security risks if not used correctly. It should only be used when you have full control over all the subdomains and trust them.

•	Limitation: This approach works well for relaxing the Same-Origin Policy for subdomains of the same site, but it doesn't work for completely different websites with unrelated domains. For that, other methods like Cross-Origin Resource Sharing (CORS) are used.

•	IFRAME: WRONG DOCUMENT PITFALL

•	Wrong Document Pitfall occurs in a context of iframes refers to situations where there is an attempt to manipulate and access the content of an iframe. 

•	Same-Origin Policy: Browsers enforce the Same-Origin Policy, which restricts web pages from making requests to a different domain, protocol, or port for security reasons. 

•	Iframe Inclusion: Websites often use iframes to embed content from another domain within their own pages. 

•	Pitfall Scenario: If a script on the parent page tries to directly manipulate the content of an iframe such as accessing its document or interacting with its elements, the Same-Origin Policy comes into play.

•	Wrong Document Error: When the parent page’s script attempts to access the iframe’s content, a security error occurs, indicating a “wrong document”error. This error happens because the browser recognizes the parent page and the iframe as separate origins.


•	Imagine you have a web page (let's call it Page A), and within that page, you have a little window that shows another web page (let's call it Page B). This little window is called an "iframe."
•	Now, the "Iframe: wrong document" pitfall happens when you try to make Page A and Page B talk to each other using JavaScript, but they can't because they belong to different "documents."
•	In its simplest form, iframe is trying to have a conversation between two people who are in separate rooms, and they can’t understand each other because they are in different places.
•	JavaScript on Page A can't easily interact with JavaScript on Page B if they are in separate iframes because they are treated as different documents by the web browser for security reasons. This can make it tricky to share information or make them work together smoothly.
•	To overcome this pitfall, you may need to use special techniques or messaging systems provided by JavaScript or the browser to allow communication between these iframes. It's like having a telephone line between those separate rooms so they can talk to each other even though they are in different places.

•	Collection: Window.Frames:

•	An alternative way to get a window object for <iframe> is to get it from the named collection window. frames: 

•	By number: window. frames[0] – window object for the first frame in the document.

•	By name: window. frames. iframeName – the window object for the frame with name=”iframeName”

![image](https://github.com/lungaHamilton09/JavaScript_Intermediate_01/assets/141244743/f840a31e-5be3-4238-b206-deac438950a0)

•	An iframe may have other iframes inside. The corresponding window objects from a hierarchy. 
•	Navigation links: 
•	window. frames – the collection of “children”window (for nested frames).
•	window. parent – the reference to the “parent”(outer) window.
•	window.top – the reference to the topmost parent window.

![image](https://github.com/lungaHamilton09/JavaScript_Intermediate_01/assets/141244743/a085fbd4-e07c-42f2-a79a-12acd50c7df4)

•	The “ SANDBOX” IFRAME ATTRIBUTE:
•	The SandBox attribute allows for the exclusion of certain actions inside an <iframe> in order to prevent it executing untrusted code. 
•	It is sandboxes the iframe by treating it as coming from another origin and applying other limitations. 
•	There is a default set of restrictions applied for <iframe sandbox src=”…”>. But it can be relaxed if we provide a space- separated list of restrictions that should not be applied as value of the attribute, like this: <iframe sandbox=”allow-forms allow-popups”>. 
•	An empty “sandbox” attribute puts the strictest limitations possible, but allows us to put a space-delimited list of those that we want to lift.

•	Below is a list of Limitations:

•	Allow-same-origin
•	By default "sandbox" forces the “different origin” policy for the iframe. In other words, it makes the browser to treat the iframe as coming from another origin, even if its src points to the same site. With all implied restrictions for scripts. This option removes that feature.
•	Allow-top-navigation
•	Allows the iframe to change parent.location.
•	Allow-forms
•	Allows to submit forms from iframe.
•	Allow-scripts
•	Allows to run scripts from the iframe.
•	Allow-popups
•	Allows to window.open popups from the iframe

•	JavaScriptinfo example
•	
•	It demonstrates a sandboxed iframe with the default set of restrictions: <iframe sandbox src="...">. It has some JavaScript and a form.
•	The purpose of the "sandbox" attribute is only to add more restrictions. It cannot remove them. In particular, it can’t relax same-origin restrictions if the iframe comes from another origin.

•	Cross Window Messaging
 
•	Cross Window Messaging allows communication between different windows (such as web pages) from various websites, overcoming the "Same Origin" restriction that typically prevents such interactions. This communication method, facilitated by the postMessage tool, ensures safety by requiring consent from both windows and the use of specific JavaScript functions.

•	The postMessage tool consists of two key components:

•	postMessage: This method enables a window to send a message to another window, essentially signaling, "I want to send you some information!" To use this, the sender employs win.postMessage(data, targetOrigin), where 'data' represents the information being sent (text, numbers, or complex data converted into text), and 'targetOrigin' specifies the destination window's address, ensuring the message reaches the intended recipient securely.

•	onmessage: The receiving window must be prepared to listen for incoming messages. Similar to having a mailbox for messages, this window is equipped with a special handler called 'onmessage.' When a sender uses postMessage, the 'onmessage' handler triggers, providing details about the message, including the content ('data'), origin (source website), and a means to reply ('source').

•	To enable this communication, the 'onmessage' handler is established using the 'addEventListener' function, ensuring effective interaction between web pages from different sources while maintaining user safety. Additionally, references to windows, whether popups or iframes, are crucial for accessing methods and content within them. For example, 'window.open' opens a new window and provides a reference, while 'window.opener' is a reference to the opening window from a popup. For iframes, 'window.frames' contains nested window objects, 'window.parent' and 'window.top' reference parent and top windows respectively, and 'iframe.contentWindow' accesses the window inside an <iframe> tag.

•	In situations where windows share the same origin (host, port, protocol), they can freely interact with each other. If they have different origins, their interactions are limited to changing the location of another window (write-only access) or posting messages. Exceptions to this rule include windows under the same second-level domain, allowing interaction when the 'document.domain' property is set accordingly, and iframes with the 'sandbox' attribute, which can be configured for specific origins to run untrusted code safely.
•	
•	The 'postMessage' interface serves as a bridge, enabling communication between windows with different origins. The sender uses 'targetWin.postMessage(data, targetOrigin)' to transmit data, with 'targetOrigin' ensuring message validation based on the recipient window's origin. When the validation is successful, the recipient window triggers the 'messageevent,' providing information about the sender's origin, a reference to the sender window, and the transmitted data. Utilizing 'addEventListener' is essential to set up the event handler in the target window, enabling seamless communication between windows from different sources.


•	Day 3: Introduction to Clickjacking:
•	Clickjacking in JavaScript is a deceptive technique technique where a malicious website tricks users into clicking something different from what they see.
•	This is done by placing an invisible or partially visible element over a legitimate website or button, making users interact with the hidden element unknowingly. 


•	For instance, a transparent button placed over a trustworthy “Download” button can lead users to click the hidden button triggering malicious actions like downloading malware or changing settings without their consent. 
•	Clickjacking exploits a user’s trust in a genuine website’s appearance and functionality, conducting harmful actions without their awareness. 
•	To mitigate this action, security measures like frame-busting scripts or the X-Frame-Options HTTP header are employed to prevent a webpage from being displayed within an iframe on another site.

•	Framebusting: 

•	Framebusting is technique used to prevent a webpage from being displayed within a frame or iframe on another website. It protects a website from unauthorized contexts such as frames on malicious websites.

•	JavaScript code detects attempts to load the website within a frame on another site and redirects the browser to the website’s URL, breaking out of the frame. This prevents the website’s content from being framed without permission, preserving security and functionality. 

•	Blocking Top Navigation: 

•	Blocking top navigation prevents a malicious site from tricking users into navigating to a different webpage without their consent. 

•	By overlaying deceptive elements and attempting to change the browser’s URL after a user click, clickjacking attacks can redirect users to harmful sites.

•	Blocking top navigation ensures that the browser won’t navigate to a different webpage without explicit user confirmation, enhancing security against clickjacking attacks.

•	Sandbox Attribute: 

•	The sandbox attribute in web development acts like a protective bubble for iframes, restricting their capabilities. By default, iframes with the sandbox attribute can’t change the main webpage’s location. 

•	Adding specific permissions like “allow-scripts allow-forms” allows limited interactivity inside the iframe but still prevents the iframe from altering the main web page’s location. 

•	This security measure ensures that only external code can change the main web page’s location, maintaining control and security. 


•	X-Frame-Options:

•	The X-Frame-Options header is a server-side directive that manages whether a webpage can be shown within a frame or iframe, serving as a security measure against clickjacking attacks. 

•	This type of attack, an attacker deceives users into clicking on something on a malicious site by covering it with a seemingly genuine frame.

•	The X-Frame-Options header offers three potential values:

•	DENY: This value instructs browsers to never display the page inside a frame, preventing its embedding in any other website. 

•	SAMEORIGIN: With this value, the page can be exhibited within a frame only if the parent document originates from the same origin, referring to the combination of protocol, domain, and port. For example, if the parent document ishttps://example.com, ,  the page can be framed on  https://example.com, but not on any other domain.

•	ALLOW-FROM domain: This value permits the page to be displayed inside a frame if the parent document is from the specified domain. For instance, if the header is set to ALLOW-FROM https://example.com,the page can be shown within a frame on https://example.com,but not on any domain. 



•	SAMESITE COOKIE ATTRIBUTE
•	The samesite cookie attribute is used to prevent clickjacking attacks. When a cookie has the samesite attribute, it will only be sent to a website if it is opened directly, not through a frame or iframe from another site. 

•	This means that if a site like Facebook has the samesite attribute on its authentication cookie, the cookie will not be sent when Facebook is opened in an iframe from another site. This prevents clickjacking attacks from being successful.

•	However, it's important to note that the samesite attribute only has an effect when cookies are used. If a website does not use cookies for authentication, it may still be vulnerable to clickjacking attacks. For example, an anonymous polling website that prevents duplicate voting by checking IP addresses would still be vulnerable to clickjacking because it does not authenticate users using cookies.


•	In summary , the samesite cookie attribute helps prevent clickjacking attacks by ensuring that cookies are only sent to the website when it is opened directly, not through a frame or iframe from another site. However, it does not provide protection if the website does not use cookies for authentication.


•	DAY 4:ARRAY BUFFER AND BINARY ARRAYS

•	ArrayBuffer
•	In simple terms, an ArrayBuffer in JavaScript is like an empty container that can hold a fixed amount of binary data (zeros and ones). It doesn't store any actual data but provides a space to put binary information. Think of it as an empty box with a specific size where you can later fill in data.

•	In web development, binary data is often encountered when working with files (creating, uploading, downloading) or performing tasks like image processing. JavaScript allows us to handle binary data efficiently, although it might seem a bit confusing due to the various classes involved.
•	The fundamental binary data object in JavaScript is called an "ArrayBuffer." Think of it as a reference to a fixed-size block of memory. 

Example:
![image](https://github.com/lungaHamilton09/JavaScript_Intermediate_01/assets/141244743/ccedc464-fa3d-4a83-af95-e6319ea4f5b8)


•	This line of code allocates a continuous block of memory with 16 bytes and initializes them to zeros.
•	It's important to note that an ArrayBuffer is not an array like you might be familiar with in JavaScript. It has some key differences:
•	Fixed Length: An ArrayBuffer has a fixed length, and you can't change its size once created.
•	Memory Space: It occupies exactly the amount of memory specified during creation, not more or less.
•	To access the individual bytes within an ArrayBuffer, you need to use a "view" object. Think of these view objects as "eyeglasses" that provide an interpretation of the bytes stored in the ArrayBuffer.
•	Here are a few common view objects:
•	Uint8Array: This treats each byte in the ArrayBuffer as a separate number, ranging from 0 to 255. Each of these numbers is an "8-bit unsigned integer."
•	Uint16Array: It treats every 2 bytes as an integer, with values ranging from 0 to 65535, known as a "16-bit unsigned integer."
•	Uint32Array: It interprets every 4 bytes as an integer, with values from 0 to 4294967295, called a "32-bit unsigned integer."
•	Float64Array: This view treats every 8 bytes as a floating-point number with a wide range of possible values.
•	So, if you have an ArrayBuffer of 16 bytes, you can choose how to interpret it. You can treat it as 16 separate "tiny numbers," 8 larger numbers (2 bytes each), 4 even larger numbers (4 bytes each), or 2 high-precision floating-point values (8 bytes each).
•	In summary, ArrayBuffer is the core binary data object in JavaScript. It represents raw binary data, and to work with it effectively, you use view objects to interpret and manipulate the data as needed.
•	



•	TypedArray Methods:
•	In simple terms, a TypedArray in JavaScript is like a set of special tools you can use to work with binary data stored in an ArrayBuffer. 
•	These tools help you interpret and manipulate the data in specific ways, treating it as numbers or other data types, making it easier to work with binary information.
•	They are much more like regular arrays: have indexes and iterable.
•	TypedArray in JavaScript is like a collection of tools for handling binary data efficiently. These TypedArrays are similar to regular arrays, meaning they have indexes and can be iterated over.
•	There are different ways to create TypedArrays, and they behave differently based on how you create them:
•	If you provide an ArrayBuffer as an argument, the TypedArray is created to work with that specific memory space. You can also specify a starting position (byteOffset) and a length to work with only a portion of the ArrayBuffer.
•	If you provide an array or array-like object, a TypedArray of the same length is created, and the data is copied into it. This is handy for initializing the TypedArray with existing data.
•	If you provide another TypedArray, a new TypedArray of the same length is created, and values are copied from the source TypedArray. The values may be converted to match the new data type if necessary.
•	If you provide a numeric argument (length), it creates a TypedArray with the specified number of elements. The size in bytes of each element is determined by the data type, and the total byte length is calculated accordingly
•	If you create a TypedArray without any arguments, it creates an empty TypedArray with zero elements.
•	To access the underlying ArrayBuffer, you can use properties like arr.buffer, which references the ArrayBuffer, and arr.byteLength, which tells you the length of the ArrayBuffer.
•	Here are some common TypedArray types:
•	Uint8Array, Uint16Array, Uint32Array: For unsigned integer numbers of 8, 16, and 32 bits, respectively.
•	Uint8ClampedArray: For 8-bit integers that are "clamped" to a specific range upon assignment.
•	Int8Array, Int16Array, Int32Array: For signed integer numbers, which can be negative.
•	Float32Array, Float64Array: For signed floating-point numbers of 32 and 64 bits, respectively.
•	It's important to note that JavaScript doesn't have single-valued types like "int" or "int8" as seen in other programming languages. TypedArrays are not arrays of individual values but views on an underlying ArrayBuffer, which makes them efficient for working with binary data.
•	Out-of-bounds behaviour
•	out-of-bounds behavior in JavaScript refers to what happens when you try to access an element in an array or collection using an index that doesn't exist within that array or collection.
•	Imagine you have an array with five elements, and you try to access the sixth element by using an index of 5. This is considered an out-of-bounds access because there is no element at that index. 
•	In JavaScript, when you perform such an out-of-bounds access, you typically get an "undefined" result, meaning there is no value at that location in the array.
•	TypedArray methods
•	TypedArrays in JavaScript behave a lot like regular arrays in many ways. You can use familiar methods like iterate (loop through), map (transform elements), slice (get a portion), find (locate an element), and reduce (aggregate values).
•	However, there are some differences:
•	No splice: You can't remove or "delete" elements from a TypedArray because they are views on a fixed, continuous block of memory. The only thing you can do is assign a value of zero to replace an element.
•	No concat method: TypedArrays don't have a built-in way to combine or concatenate them directly.
•	In addition to the regular array methods, there are two special methods for TypedArrays:
•	arr.set(fromArr, [offset]): This method copies all elements from fromArr into arr, starting at a specified position (offset). By default, it starts from the beginning (offset 0).
•	arr.subarray([begin, end]): This method creates a new view of the same data type, but only for a specific portion of the TypedArray, defined by the begin and end positions. Unlike slice, it doesn't copy the data; it just provides a different view for working with a specific part of the data.
•	These additional methods enable you to copy data between TypedArrays, create new views on existing data, and manipulate TypedArrays effectively while taking into account their underlying memory structure.

•	DATAVIEW:
•	 DataView in JavaScript is like a versatile tool for reading and interpreting binary data stored in an ArrayBuffer. It's "untyped," meaning you can use it to access data at any position and in any data format within the ArrayBuffer.
•	Here's how it works:
•	Underlying ArrayBuffer: DataView needs an existing ArrayBuffer with the binary data. Unlike typed arrays, it doesn't create its own buffer; you must provide one.
•	Byte Offset: You can specify a starting position (byteOffset) within the ArrayBuffer where the DataView should begin reading data. By default, it starts at the beginning (byteOffset 0).
•	Byte Length: You can also specify how many bytes the DataView should cover (byteLength). By default, it extends until the end of the buffer.
•	Now, here's where DataView differs from typed arrays:
•	Typed arrays have a fixed data format determined when you create them (e.g., Uint8Array, Uint16Array). All elements in the array must follow that format.
•	DataView, on the other hand, allows you to choose the data format (like 8-bit or 16-bit) at the time you read the data, using methods like .getUint8(i) or .getUint16(i). This means you can read different parts of the data in various formats within the same ArrayBuffer.
•	So, in summary, DataView is like a flexible reader that can access binary data in any format at any position within an ArrayBuffer, making it highly adaptable for working with diverse data structures.





