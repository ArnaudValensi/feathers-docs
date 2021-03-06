# Feathers vs. Meteor

Both Feathers and Meteor are real-time JavaScript platforms that provide front end and back end support. They both allow clients to send and receive messages over websockets. Feathers lets you choose which real-time transport(s) you want to use via [socket.io](../../real-time/socket-io.md) or [Primus](../../real-time/socket-io.md), while Meteor relies on SockJS.

Feathers is completely open source and is community supported, whereas Meteor, although open source, is venture backed and has raised $31.2 million to date.

Meteor only has official support for MongoDB but there are some community modules of various levels of quality that support other databases. Meteor has it's own package manager and package ecosystem. They have their own template engine called Blaze which is based off of Mustache along with their own build system, but also have guides for Angular and React.

Feathers has official support for [many more databases](../../databases/readme.md) and supports any front-end framework or view engine that you want. We have [guides](../../guides/readme.md) for integrating Feathers with many of the most popular.

Feathers uses the defacto JavaScript package manager [npm](http://npmjs.org). As a result you can utilize the hundreds of thousands of modules published to npm. Feathers lets you decide whether you want to use Gulp, Grunt, Browserify, Webpack or any other build tool.

Meteor has optimistic UI rendering and oplog tailing whereas currently Feathers leaves that up to the developer. However, we've found that being universal and utilizing websockets for both sending and receiving data alleviates the need for optimistic UI rendering and complex data diffing in most cases.

Both Meteor and Feathers provide support for email/password and OAuth authentication. Once authenticated Meteor uses sessions maintain a logged in state, whereas Feathers keeps things stateless and uses [JSON Web Tokens](https://jwt.io/) (JWT) to assess authentication state.

One big distinction is how Feathers and Meteor provide real-time across a cluster of apps. Feathers does it at the service layer or using another pub-sub service like Redis whereas Meteor relies on having access to and monitoring MongoDB operation logs as the central hub for real-time communication.