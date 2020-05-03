# WebSockets

**WebSocket**: WebSocket is bidirectional, a full-duplex protocol that is used in the same scenario of client-server communication, unlike HTTP it starts from ws:// or wss://. It is a stateful protocol, which means the connection between client and server will keep alive until it is terminated by either party (client or server). after closing the connection by either of the client and server, the connection is terminated from both the end.

-- Source: [What is web socket and how it is different from the HTTP?](https://www.geeksforgeeks.org/what-is-web-socket-and-how-it-is-different-from-the-http/)



### NPM modules
- [socket.io](https://github.com/socketio/socket.io)
- [ws](https://github.com/websockets/ws)


### WebSockets Docs
- [WebSockets Methods for Real-Time Data Streaming](https://os.alfajango.com/websockets-slides/#/)
- [Full Stack Python - WebSockets](https://www.fullstackpython.com/websockets.html)
- [MDN - Writing WebSocket client applications](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API/Writing_WebSocket_client_applications)
- [Tutorials Point - HTML5 WebSocket](http://www.tutorialspoint.com/html5/html5_websocket.htm)
- [WebSocket.org](http://www.websocket.org/)

- [websocket-stream](https://github.com/maxogden/websocket-stream)


- [Sina UED: WebSocket实战](http://ued.sina.com.cn/?p=900)
- [使用 HTML5 WebSocket 构建实时 Web 应用](https://www.ibm.com/developerworks/cn/web/1112_huangxa_websocket/)
- [使用Node.js+Socket.IO搭建WebSocket实时应用](http://www.plhwin.com/2014/05/28/nodejs-socketio/)
- [WebSocket —— 为Web应用带来桌面应用般的灵活性](http://www.infoq.com/cn/articles/websocket-desktop-agility-web-applications)
- [使用 WebSockets 的 9 个应用场景](http://www.oschina.net/translate/9-killer-uses-for-websockets)


### WebSockets vs HTTP

Source: [rfc6455: The WebSocket Protocol](https://tools.ietf.org/html/rfc6455)
>  The WebSocket Protocol is an independent TCP-based protocol.  Its
   only relationship to HTTP is that its handshake is interpreted by
   HTTP servers as an Upgrade request.
>  By default, the WebSocket Protocol uses port 80 for regular WebSocket
   connections and port 443 for WebSocket connections tunneled over
   Transport Layer Security (TLS)
 
Source: [What is web socket and how it is different from the HTTP?](https://www.geeksforgeeks.org/what-is-web-socket-and-how-it-is-different-from-the-http/)

__HTTP protocol__: HTTP is __unidirectional__ where the client sends the request and the server sends the response. Let’s take an example when a user sends a request to the server this request goes in the form of HTTP or HTTPS, after receiving a request server send the response to the client, each request is associated with a corresponding response, after sending the response the connection gets closed, each HTTP or HTTPS request establish the new connection to the server every time and after getting the response the connection gets terminated by itself.
HTTP is __stateless__ protocol runs on the top of TCP which is a connection-oriented protocol it guarantees the delivery of data packet transfer using the three-way handshaking methods and re-transmit the lost packets.
HTTP can run on the top of any reliable connection-oriented protocol such as TCP, SCTP. When a client sends HTTP request to the server, a TCP connection is open between the client and server and after getting the response the TCP connection gets terminated, each HTTP request open separate TCP connection to the server, for e.g. if client send 10 requests to the server the 10 separate HTTP connection will be opened. and get closed after getting the response/fallback.
 
__WebSocket__: WebSocket is bidirectional, a full-duplex protocol that is used in the same scenario of client-server communication, unlike HTTP it starts from ws:// or wss://. It is a stateful protocol, which means the connection between client and server will keep alive until it is terminated by either party (client or server). after closing the connection by either of the client and server, the connection is terminated from both the end.
