# Fundamentals of How Web Works
1. How a Website is loaded?

(a) the first process : DNS Lookup : when we enter a website address in the browser, it searches for the IP Address it is hosted on, that IP Adress is attached to the server which holds the files of our app, then our browser makes a HTTP request to that server, and in the response Server sends the files. these files are mostly HTML. then browser put these files in a process called Critical Rendering Path.
(b) then Browser starts to parse that HTML file to create the DOM, it doesn't even wait for the HTML to be fully loaded in the browser. DOM is like a tree of HTML elements.
(c) While parsing HTML if it encounters a CSS file, then it stop the parsing HTML, and go on to download CSS file and parse it to create the CSSOM. after completing it browser again resume parsing HTML.
(d) Now while all this is going, if browser encounters a script (mostly inside the body) then it will stop the HTML CSS parsings and go on to download JS file and make it ready for the DOM. So to avoid this blocking nature of the script we can use Async and Defer attributes on the script tag. Async tells to the browser that while the JS file is being loaded, you can continue to parse the HTML, but then Browser decides when to attach JS codes to the DOM elements, so the order of script execution is handled by browser and can not be predicted.
(e) But if we Defer, then browser will parallaly do both the Parsing of HTML and Loading of script and after creating the complete DOM it attaches the Script manipulations to them. So it is best to use the defer, because if we attach the script to the body then after all HTML parsing, browser loads the script first and then executes it.
(f) then after creation of DOM and CSSOM it combines them to create Render Tree. then based on Render Tree, Browser does Layouting, in Layouting it basically decided the size and position of each element in the given screen.
(g) and then finally it renderes everything out in 60FPS and this last process is called Paint.

2. Where are servers located?

: Mostly in Data Centres built by tech giants like Amazon, Google, Microsoft. And these centres holds a lot of computer which are personalised to store data very efficiently and in a fast manner and connceted to the internet 24*7.

3. What are Web Sockets?

: A App is the combination of the front-end and back-end. and to get something to the or from the backend we need to do a HTTP request. In that request we send or request some data, that request is ended and considered sucessful, when that data or request has reached the server. To get a piece of a data from the server, server has to make another conncetion to the client. It is exactly works like letters you send the letter and wait for another to come. Sounds inefficient.
: To solve this Web Sockets came into picture. It works like live data sharing, exactly like a phone call. Where the client and server are conceted the whole time after the first hand shake. and they share data and requests all the time continously. So is it the optimal solution. The answer really depends. Web Sockets are not that much scalable. Because the server has to be active all the time, compare to the HTTP way, where it can entertain one client and then move on to the next.
: But still web sockets are used in scale. Because when it is needed, it has to be used. A prime example is Whatsaap. It still uses web sockets, because in a chat app the sending and recieving of messages happens in real time and it has to be that way only.