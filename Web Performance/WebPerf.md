1. Critical Rendering Path :

(a) the first process : DNS Lookup : when we enter a website address in the browser, it searches for the IP Address it is hosted on, that IP Adress is attached to the server which holds the files of our app, then our browser makes a HTTP request to that server, and in the response Server sends the files. these files are mostly HTML. 

(b) then Browser starts to parse that HTML file to create the DOM, it doesn't even wait for the HTML to be fully loaded in the browser. First Browser converts the HTML code into Response, then to tokens, then to nodes, then to final DOM. Every tag from HTML denotes a node. So we can say that, one open-tag with one close-tag form a node, hence, every node can have node children, so it look like a hireachy and this also why DOM is called a TREE.

(c) While parsing HTML if it encounters a CSS file, then it stop the parsing HTML, and go on to download CSS file and parse it to create the CSSOM. after completing it browser again resume parsing HTML. But CSS parsing is not partial, it means to parse it, browser needs the whole file. Also parsing CSS pauses every thing, HTML or JS parsing. It mean it is render blocking. So how to optimise it?

(d) First is Inline CSS, then Media Queries. Also, in CSS generic selectors takes lesser time than more specific selectors. For an example applying color to all H1, but bhen the selector is nested or specific, then it needs to go inside the DOM tree to find that element. (CSS Parsing : CSS Code -> Characters -> Tokens -> Nodes -> CSSOM)

(e) Now while all this is going, if browser encounters a script (mostly inside the body) then it will stop the HTML & CSS parsings and go on to download JS file and make it ready for the DOM. Hence, JS downloading is Parser Blockinhg. So to avoid this blocking nature of the script we can use Async and Defer attributes on the script tag. Async tells to the browser that while the JS file is being loaded, you can continue to parse the HTML, but then Browser decides when to attach JS codes to the DOM elements, so the order of script execution is handled by browser and can not be predicted.

(f) But if we Defer, then browser will parallaly do both the Parsing of HTML and Loading of script and after creating the complete DOM it attaches the Script manipulations to them. So it is best to use the defer, because if we attach the script to the body then after all HTML parsing, browser loads the script first and then executes it.

(g) then after creation of DOM and CSSOM it combines them to create Render Tree. then based on Render Tree, Browser does Layouting, in Layouting it basically decided the size and position of each element in the given screen.

(h) and then finally it renderes everything out in 60FPS and this last process is called Paint.

(i) If we want to see all these processes in Action then we can use Timeline tab of Chrom Dev Tools.

(j) To optimise the HTML, CSS, JS we can minify the codes, compress the files, and cache the final nodes.

(k) But if the script tag is syncrnous in nature, then browser will pause CSS or HTML parsing, to download the file and then CSS Parsing will be resumes, then JS parsing will start, and then finally HTML parsing gets completed.
