# Week1
•	Week 0: Intermediate JavaScript – Introduction to Intermediate JavaScript
 
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

