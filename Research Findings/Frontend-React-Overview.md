# React on a Go backend

React’s standard flow is to start with an empty HTML template from the server, and populate the DOM entirely on the client. Letting React pre-render the initial HTML for your app on the server before the client takes over has some advantages, though: it lets slower (mobile) clients load your app much faster, and it’s good for SEO for search engines that don’t support JavaScript. Since you have to run React on the server to do this, you need a JavaScript-able backend, which is why such Universal (a.k.a. Isomorphic) apps are mostly built with Node.js backends. However, you can create universal React apps with other languages too, including Go. In this post, I’ll walk through an example of a universal React app running on a Google App Engine Standard Go backend (which is slightly more constrained than a regular Go server).


## Notable features

#### One-way data flow

Properties (commonly, props) are passed to a component from the parent component. Components receive props as a single set of immutable values[10] (a JavaScript object). Whenever any prop value changes, the component's render function is called allowing the component to display the change.

#### Virtual DOM

Another notable feature is the use of a "virtual Document Object Model", or "virtual DOM". React creates an in-memory data structure cache, computes the resulting differences, and then updates the browser's displayed DOM efficiently.[11] This allows the programmer to write code as if the entire page is rendered on each change, while the React libraries only render sub components that actually change.

#### Lifecycle Methods

Lifecycle methods are various methods that come built in with ReactJS. They allow the developer to process data at various points in the lifecycle of a React app. For example
* shouldComponentUpdate is a lifecycle method that tells Javascript to update the component using a boolean variable.
* componentWillMount is a lifecycle method that tells Javascript to set up certain data before a component mounts (is inserted into the virtual DOM).
* componentDidMount is a lifecycle method which is similar to componentWillMount except that it runs after the render method and can be used to add JSON data and to define properties and states.
* render is the most important lifecycle method and the only required one in any component. The render method is what connects with the JSX and this method can display its own JSX.

#### JSX

JavaScript XML (JSX) is an extension to the JavaScript language syntax[12]. Similar in appearance to HTML, JSX provides a way to structure component rendering using syntax familiar to many (if not most) developers. React components are typically written using JSX, although they do not have to be (components may also be written in pure JavaScript). JSX is similar to another extension syntax created by Facebook for PHP, XHP.



### References

* https://el-tramo.be/blog/react-go-gae/
* https://en.wikipedia.org/wiki/React_(JavaScript_library)
