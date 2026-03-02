# Test 1 - In Class Review
- visual studio code, live preview plugin
- no co-piolt, no auto generoate
- localhost:3000/static/index.html

- generator function - you can think of it as an array, it yeilds an item, useful for long running requests
- immediatly invoked function - called right after ()
- will have to use debugger
- list of url, and wanted to get the data from the url.
- I've got 3 urls.
- fetch('https://api.jopnick.com')
- comes back with Promis {<pending>}
- const result = await fetch('https://api.jopnick.com');
- object comes back, response
- const result2 = await fetch('https://api.jopnick.com').then( res => res.json());
- comes back array of url

- result2.links.map( link => link?.href )
- ? is a conditional, if any href aren't there, it won't blow up

-  result2.links.map( link => fetch(link?.href) )
-  Promise.all( result2.links.map( link => fetch(link?.href).then (res => res.json()) ) )

-  two way to do any promise, you can get data by .then or awaiting it
-  await Promise.all( result2.links.map( link => fetch(link?.href).then (res => res.json()) ) )
-  if you use await, you need an asnyc

-  var is function scopped, it gets hoisted. even if you put it in a for loop, it still exists.
-  const and let are blocked scopped.

-  promise.allsettled - returns everything, fail or success
-  promise.all - if one fails, all fail
-  promise.race - the first one to work
-  promise.any
