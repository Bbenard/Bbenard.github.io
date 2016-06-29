layout:  post
title: Chrome Development Tools
---
 *Introduction*
 
  Google Chrome is a rich and powerful web browser, pioneering what is possible for applications on the web. Google has worked hard to deliver a very fast, very stable, feature rich browsing experience for end users. Google has also ensured that developers like you have a great experience with Chrome. The Developer Tools, bundled and available in Chrome and 
  Safari, allows web developers and programmers deep access into the internals of the browser and their web application.
  
 *Overview*
 
 Overall, there are eight main groups of tools available view Developer Tools, and the capabilities are being extended with every release. Chrome 5 now offers Elements, Resources, Scripts, Timeline, Profiles, Storage, Audits, and Console.
 *Elements*
 
 The Elements tool allows you to see the web page as the browser sees it. That is, using the Elements tool, you can see the raw HTML, raw CSS styles, the Document Object Model, and manipulate either in real time.
 
 *Resources*
 
 Use the Resources tool to learn what components your web page or application is requesting from web servers, how long these requests take, and how much bandwidth is required. You can also view the HTTP request and response headers for each of your resources. The Resources tool is perfect for helping you speed up page load times. 
 
 *Scripts*
 
 To peer inside the JavaScript for a page, you will use the Scripts tool. Here you can find a list of scripts required by the page plus a full featured script debugger. You can even change the JavaScript on the fly! Read more in Part Two, coming soon.
 
 *Timeline*
 
 For advanced timing and speed analysis, the Timeline tool offers in-depth visibility into the various Chrome behind-the-scenes activities. You can learn how long the browser takes to handle DOM events, rendering page layouts, and paint the window.
 
*Profiles*

The Profiles tool helps you capture and analyze the performance of JavaScript scripts. For example, you can learn which functions take the most time to execute and zero in on exactly where to optimize

*Storage*

Modern web applications require more persistence than simply cookies, and the Storage tool helps you track, query, and debug local browser storage. This tool can display and query data stored in local databases, local storage, session storage, and cookies.

*Audit*
The Audit tool is like having your own web optimization consultant sitting next to you. This tool can analyze a page as it loads and provide suggestions and optimizations for decreasing page load time and increase perceived (and real) responsiveness

*Console*
Last but definitely not least, the Developer Tools offers a full featured Console. From the Console, you can enter arbitrary JavaScript and programmatically interact with your page

#####Starting Up
It's easy to start the Developer Tools while inside Chrome.

For any operating system, you can simply right-click on any element in the page and select the "Inspect Element" option from the context menu. This will open the Developer Tools and drill right to the element you clicked on.

Finally, you can choose to open the tools from the main browser menu.

On a Mac, and from the main application menu bar, select View, Developer, Developer Tools.
You may also open the Developer Tools with a simple keyboard shortcut. Depending on your operating system, try the following:

On Windows and Linux, select the Control-Shift-J keys.
On Mac, select the Command-Option-J keys.

*Summary on Elements*
There is a lot of functionality available via the Elements Tab,

You should use the Elements Tab when you want to see how the page looks to the browser itself. Common problems such as "how is this style computed?" or "what HTML tags generated this component?" are quickly and easily answered via the Elements Tab.

Think of the Elements Tab like an uber-"view source", and gain very sharp visibility into your page.

After you've investigated the page, you might be wondering how HTML, CSS, and images got there in the first place. The Resources Tab, described next, shows you how the client browser and web server communicate to send over those resources.

*Resources*
Once your application is functioning, your next step should be to optimize the network and bandwidth performance. You should aim to make the transfer of your application, from server to client, as fast and as efficient as possible. Your users will thank you for the fast page loads, you'll save money on bandwidth and server resources, and you'll also score better in Google's search result ranks (which now take into account site speed).

The Resources Tab in Developer Tools is your window into the communication between web server and client browser. You are able to see all of the resources requested by the browser (this is always very surprising!), the time it takes to receive them from the server, and how much bandwidth is used during the transfer.

Ironically, running the Resources Tab affects page load performance, so it is disabled by default. The first time you access the functionality, you will need to enable it for the page you are viewing.

*Summary Resources*
There is a lot more to the Resources tab, which we will cover in a future article.

Use the Resources Tab to gain visibility into how your client browser is communicating with the web server. Using this information, including request time, request size, and request order, you can make smart optimizations to reduce server load, costs, and increase speed and enhance user experience.

Speed is very important for your web site, your users, and search engines. Once you have the number and size of resources reduced, and the appropriate HTTP conversations occurring, the next step is to investigate and optimize the scripts that are running in your page. Luckily, the Scripts tab, discussed next, does just that.



 

