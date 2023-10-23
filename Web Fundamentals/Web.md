# Fundamentals of How Web Works

1. How a Website is loaded?

(a) the first process : DNS Lookup : when we enter a website address in the browser, it searches for the IP Address it is hosted on, that IP Adress is attached to the server which holds the files of our app, then our browser makes a HTTP request to that server, and in the response Server sends the files. these files are mostly HTML. then browser put these files in a process called Critical Rendering Path.
(b) Look for WebPerf file to know what is Critical Rendering Path.

2. Where are servers located?

: Mostly in Data Centres built by tech giants like Amazon, Google, Microsoft. And these centres holds a lot of computer which are personalised to store data very efficiently and in a fast manner and connceted to the internet 24*7.

3. What are Web Sockets?

: A App is the combination of the front-end and back-end. and to get something to the or from the backend we need to do a HTTP request. In that request we send or request some data, that request is ended and considered sucessful, when that data or request has reached the server. To get a piece of a data from the server, server has to make another conncetion to the client. It is exactly works like letters you send the letter and wait for another to come. Sounds inefficient.
: To solve this Web Sockets came into picture. It works like live data sharing, exactly like a phone call. Where the client and server are conceted the whole time after the first hand shake. and they share data and requests all the time continously. So is it the optimal solution. The answer really depends. Web Sockets are not that much scalable. Because the server has to be active all the time, compare to the HTTP way, where it can entertain one client and then move on to the next.
: But still web sockets are used in scale. Because when it is needed, it has to be used. A prime example is Whatsaap. It still uses web sockets, because in a chat app the sending and recieving of messages happens in real time and it has to be that way only.

4. What is Page Lifecycle in Browser?

(a) The page lifecycle in browsers and web pages refers to the sequence of states a webpage goes through from the time it's loaded in the browser until it's closed. It's a crucial concept for developers as it provides signals about transitions between lifecycle states, allowing them to manage resources and user experience effectively.
(1) Active: A page is in the active state if it is visible and has input focus. This is the state when the user is actively interacting with the webpage
(2) Passive: A page is in the passive state if it is visible but does not have input focus. This usually means the user is viewing the page but not interacting with it
(3) Hidden: A page is in the hidden state if it is not visible and has not been frozen, discarded, or terminated. This usually happens when a user switches tabs or minimizes the browser
(4) Frozen: In the frozen state, the browser suspends execution of tasks in the page's task queues until the page is unfrozen. This state is used to preserve CPU/battery/data usage
(5) Discarded: A page is moved to the discarded state typically from the frozen state to conserve resources. In this state, the page is completely unloaded from memory, but can be restored if the user navigates back to it