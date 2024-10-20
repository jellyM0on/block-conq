# test locally 

## set up client 
- navigate to the /client directory 
- run in terminal: npm install 
- run in terminal: http-server -p 3000
- to navigate to a page, the url will be 'http://localhost:3000/name.html'

## set up extension 
- go to 'chrome://extensions/' 
- click 'Load unpacked' and select the /extension directory 
- click on 'service worker' to inspect logs 

# structure 

## flow 
- if a site is added, it is put in the local storage
- every time the buttons are clicked, an event is dispatched
- extension/content.js listens to these events on the text.html page 
- extension/content.js retrieves data from the local storage then passes this to background.js 
- extension/background.js listens if the user navigates to a different tab or if a tab is updated. if the url of the tab matches one of the blocked sites, it will replace the url with /blocked.html 

## notes 
- the scope of content.js is limited to text.html
- background.js encompasses the browser 
- time functionality not working. not updated yet
- url links only match to the exact given urls. not updated yet