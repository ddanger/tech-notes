# Digging Into Node (Frontend Masters, Kyle Simpson, 5/9/2019)
My notes from attending the filming of the Frontend Masters course [Digging Into Node](https://frontendmasters.com/workshops/digging-into-node/) by Kyle Simpson.

The main takeaways for me were:
 - becoming familiar with how stream processing works in Node code
 - becoming familiar with core packages to use
 - learning how to make a simple webserver without using Express
 - learning how to spawn processes in Node to create parallelism for load tests against a server
 
 I'm not sure when, if ever, I'll use this. If I ever have to do serious Node work, I may reference the video or these notes.

## Random Notes
- JS is well-suited to high throughput / low latency tasks
- Kyle was attempting to write a server-side JavaScript engine with V8 before he heard of Node. He was excited when Node was released.
- The author of Node originally was writing a system in Ruby, but found he needed something like the JS event loop, so he switched to JS to get that for free.
- Node is well-suited to usage as a "middle end" system to bridge between frontend/backend
- Add `#!/usr/bin/env node` to top of your Node script file and make executable so you can run it from cmd line without referencing `node`
- GZip compression was designed as a streaming algorithm
- Streams have events you can listen to, like "end" to know when a stream is done
- Wow `console.table()` is pretty cool for printing arrays of flat objects (e.g. any DB data)
- Debugging in Chrome:
  - Use GoogleChromeLabs/ndb or ...
  - Open Chrome and navigate to this URL: chrome://inspect/#devices
  - Launch a node script with `node --inspect <name of script file>`
  - Return to chrome and see a new row referencing the running script and an *inspect* link ... click it
  - Go to the Sources tab and click `Pause on exceptions` and check the checkbox
  - When you hit an exception, debug!
- Production tips:
  - Use "forever" or something like it to restart your node process if it dies
  - single node process SSL
  - loopback monitoring tools for node
  - the Node org ships a production hardened version of Node.
  - watch the FEM courses
    - [Full-Stack for Front-Ends](https://frontendmasters.com/courses/full-stack/)
    - [Full-stack for Front-Ends Part 2](https://frontendmasters.com/courses/full-stack-v2/)
  
## Packages Used
There are sooo many packages available in the Node ecosystem. It's good to see what someone like Kyle uses..

### Included with Node
- `path`: deal with file paths
- `fs`: deal with files
- `stream`: ability to process input and output in chunksspecifically the `Transform` function, 
- `zlib`: streaming impl of gZip/Unzip compression
- `util`: `.promisify` takes something that requires callbacks and returns one that returns promises
- `http`: to create an HTTP server
- `child_process`: spawning a process

### 3rd Party
- `minimist`: simple handling of command line params. `yargs` if you need more
- `caf`: cancelable async flows, allows you to provi
- `sqlite3`: a decent database
- `node-static-alias`: serve static files
- `node-fetch`: just like `fetch` in the browser
- `express`: ubiquitous library for web-server apps
