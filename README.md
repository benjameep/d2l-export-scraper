# d2l-export-scraper
Reads a d2l export folder and returns all the html chunks

### Can be run in the Command Line or as a module

#### In Command Line
```
> node d2l-export-scraper           // or node main.js if your inside the folder
> prompt: useNight: (false)         // Set true if you want nightmare to go grab the hard to get urls (will ask for username and password)
> prompt: folderPath: (./export)    // the folder that contains the export
> prompt: resultFile: (result.json) // where you want all the html chunks
```

#### As Module
``` javascript
var scraper = require('d2l-export-scraper')

// Without the nightmare stuff
var htmlChunks = scraper('path-to-export-folder')

// With the nightmare stuff
scraper('path-to-export-folder','path-to-auth.json',function(htmlChunks){
  // Do stuff with htmlChunks
})
```
auth.json file should look like
``` json
{
  "username":"my_cct_account_username",
  "password":"my_cct_account_password"
}
```

### Nightmare Stuff
The Nightmare stuff adds a couple more helpful urls for things like rubrics and dropboxs, but
I would only use it if you are going to use the hrefs I give you.
