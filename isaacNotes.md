    # Proxy
​
## `dist/index.html`
- The React CDN script tags are unnecessary, since React is served via your bundle. 
- Each service should have its own styles for loosely-coupled, modular CSS. This means that either Style Components or CSS Modules will need to be used to avoid CSS name collision.
​
## `src/` 
- This directory is unused, and can be removed.
​
# Microservice
​
## `/`
​
### `server.js`
- Since you aren't sending both `urlencoded` and `JSON` data from the client, you probably don't need both body parsers. Including them both slows down response times.
- You don't need `async/await` for `path.join` since this function is neither async nor returns a promise. 
​
### `package.json`
- Consider including a production-mode server starting script.
​
## `documentation/`
- I am a huge fan of all the notes you took. Consider moving all this documentation into another repo specifically for engineering journalism. 
​
## `src/`
​
### `App.jsx`
- lines 19/20: use array/object destructuring. (Also, `window` is a reserved variable name, so it'd be better to choose some other variable name)
- lines 20-30: If GET is all you need, the native `fetch()` is the best option for API calls, as it is built into the browser, and removing `jQuery` from your project will dramatically reduce the bundle size. Additionally, on lines 24-27 is an opportunity to use clever parameter naming that will allow you to make use of shorthand in the object literal passed into `this.setState`
- the `render` method: create some constants by destructuring `this.state`
​
### `TrackContainer.jsx`
- This function can be refactored to a single-line implicit return arrow function.
- `'ion-arrow-graph-up-right'` doesn't really sound like it describes popularity, or vise-versa. I think this variable name could be more descriptive.
​
### All test files
- I'd recommend placing all test files in a test directory, so that they don't clutter up your component directory. Another good option would be to place every component in its own directory, with its own test file. The latter implementation is also conducive to adding other frameworks such as `react-redux` to your project. Futher reading:
​
https://github.com/erikras/ducks-modular-redux
https://github.com/alexnm/re-ducks
​
### `AlbumInfo.test.js` and `Track.test.js` and `TrackContainer.test.js`
- I'd recommend moving the test data into another module, so it can be reused, and won't clutter your test files.
​
### `AlbumInfo.jsx`
- I'd recommend trying out `({ multiple: { layers, of: { destructuring } } }) => {};` especially since your component's name gives adequate of context to the nested properties of its props!
​
### `TrackContainer.test.js`
- I'd recommend that you check that it doesn't just have the right number of `<div/>`s, but also has the right props, or something that will specifically check that the component is rendered _with the proper information_. 
​
​
## `data/`
​
### `database.js`
- Your schema appears to lack an index! Even though albumId is supposed to function as an index, your database won't know that, and will loop over everything.
​
# GitHub Commit Practices:
- Make sure your commit messages are in _present tense_ *verb noun* format. E.g. `updated index.html with latest optimizations` should be changed to `update index.html with latest optimizations` or `optimize index.html`.
- Make sure commit messages are specific. E.g. something like `changed MyPackages.yml` should say something like `bumped react version number`. 
- Filenames can be ommitted in commit messages. The diff on the commit will reveal what files changed, so you can spend your character limit focusing on the substantive "what/why" of the change.
- Make sure commit messages refer to a single "change" (with quotation marks because this concept is a bit subjective). If you find yourself writing a commit message that says "fix foo *and* update bar" then split it up into two commits.
- This was almost never an issue, but of your 60 or so commits, about three or four included changes that were not relevant to the commit message. Resist the temptation to not commit twice!
- Once branches have been merged, you'll generally want to delete them from both the remote and local repos. They tend to build up and cause clutter.
- Make sure you do thorough code review on Pull Requests, and leave comments on any suggestions you may have. Even nitpicks are okay for FEC/SDC! Leaving PR Review comments is better than an in-person conversation, since it documents the development process better, and can be done on your own time.
​
# Overall comments
​
There are a few missing features which absolutely need be included when you have time to come back to this project: 
​
- Serverside Rendering
- CSS Modules or Styled Components
​
It seems you were very close to finishing SSR, and I hope you put the finishing touches on it when there's time!
​
As for the CSS, it is vital that writing CSS for your service's components not require knowledge of all other CSS that it will be loaded in with. A site-wide "monolithic" stylesheet becomes very difficult to maintain quite rapidly, as the odds of name-collision errors within a single file increase as the project grows. The browser doesn't create a new global namespace for a new stylesheet, so even splitting styles into multiple stylesheets is problematic unless you also use style components or CSS Modules.
​
I also want you to know how to deploy to AWS with EBS or Docker and EC2. You'll be deploying at least a few times during SDC, and I think it may be a good challenge for you during SDC to attempt to do your deployments using Docker/DockerHub. 
 
I think you've done a great job, and you've come a long way since the TA! Most of my notes are minor nitpicks and suggestions for code organization/clarity.