


# PWA-JATE
|HTML,Javascript  |[Git Hub Repo](https://github.com/eogbeide424/PWA-JATE|) 
|Deployed App Link | |[Deployed App](https://frozen-reef-29437.herokuapp.com/)

## Description

 On this project we had to add to the code given and make sure that when we enter npm start at the root directory 1. the server starts 2. the JavaScript files gets bundled using webpack 3. make sure that IndexDb immeadiately creates a database storage  4. when  you click off the dom  window that the data has been saved  5. then when you click the install button that the application saves  onto your desktop . At first  it was confusing seperating the client from the server and making sure that build run smoothly without error what I came to find out is thtat the package.json had a lot to do with it . If the root package.json dosen't have the correct scripts(refer to the snippet below) then it would not build run or anything it'll just give you an error message.
 ````javascript
 "scripts": {
    "start:dev": "concurrently \"cd server && npm run server\" \"cd client && npm run dev\"",
    "start": "npm run build && cd server && node server.js",
    "server": "cd server nodemon server.js --ignore client",
    "build": "cd client && npm run build",
    "install": "cd server && npm i && cd ../client && npm i",
    "client": "cd client && npm start"
  },
  ````
Another thing to note was how idb used the built in methods of openDb to handle request similar to how an API server does with a put request to update and a get request to retrieve, I didn't have to utillize it in this particular project but you can even do a Delete and post request 
````javaScript
export const getDb = async () =>{
console.error('getDb not implemented');
const jateDb = await openDB('JATE', 1);
const tx = jateDb.transaction('jate', 'readwrite');
const store = tx.objectStore('jate');
const request = store.get('id');
const result = await request;
console.log(result);
}
````
Learning how to do this manually makes me appreciate the fact that React does all this under the hood for you 

## Table of Contents 

* [Installation](#installation)
* [Usage](#usage)
* [Credits](#credits)
* [License](#license)


## Installation

When open the app open the terminal from the root folder and run a npm start


## Usage 

It's basically just another text editor you can save code snippets or use it to write notes and to have it function off line just install the app on your device 



## Credits

Eugene Ogbeide eogbeide2@gmail.som

## License

MIT

'https://choosealicense.com/licenses/MIT/

undefined



---

🏆 The sections listed above are the minimum for a good README, but your project will ultimately determine the content of this document. You might also want to consider adding the following sections.

## Badges


https://img.shields.io/badge/license-MIT-red

## Questions
If any questions on how to use the app you can email me at eogbeide2@gmail.som

© 2023 edX Boot Camps LLC. Confidential and Proprietary. All Rights Reserved.
