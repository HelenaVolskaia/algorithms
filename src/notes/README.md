# README

- [README](#readme)
  - [Event Propagation, Event Delegation](#event-propagation-event-delegation)
  - [Closure](#closure)
  - [TCP & UDP](#tcp--udp)
  - [Javascript new operator](#javascript-new-operator)
  - [CSS vertical align](#css-vertical-align)
    - [vertical align with pseudo elements](#vertical-align-with-pseudo-elements)
  - [Javascript Prototype](#javascript-prototype)
  - [React vs Vue](#react-vs-vue)
    - [Composition of components](#composition-of-components)

## Event Propagation, Event Delegation

<img height="600" src="assets/event-propagation.svg">

## Closure

A closure is an inner function that has access to variables outside of its scope.

A closure is a function that can remember environments when it was created.

## TCP & UDP

- https://support.holmsecurity.com/hc/en-us/articles/212963869-What-is-the-difference-between-TCP-and-UDP-

What is the difference between TCP and UDP?

The network scanner supports TCP and UDP. Here is some information about TCP and UDP and the differences between the different protocols.

General
Both TCP and UDP are protocols used for sending bits of data — known as packets — over the Internet. They both build on top of the Internet protocol. In other words, whether you are sending a packet via TCP or UDP, that packet is sent to an IP address. These packets are treated similarly, as they are forwarded from your computer to intermediary routers and on to the destination.

TCP and UDP are not the only protocols that work on top of IP. However, they are the most widely used. The widely used term “TCP/IP” refers to TCP over IP. UDP over IP could just as well be referred to as “UDP/IP”, although this is not a common term.

TCP
TCP stands for Transmission Control Protocol. It is the most commonly used protocol on the Internet.

When you load a web page, your computer sends TCP packets to the web server’s address, asking it to send the web page to you. The web server responds by sending a stream of TCP packets, which your web browser stitches together to form the web page and display it to you. When you click a link, sign in, post a comment, or do anything else, your web browser sends TCP packets to the server and the server sends TCP packets back. TCP is not just one way communication — the remote system sends packets back to acknowledge it is received your packets.

TCP guarantees the recipient will receive the packets in order by numbering them. The recipient sends messages back to the sender saying it received the messages. If the sender does not get a correct response, it will resend the packets to ensure the recipient received them. Packets are also checked for errors. TCP is all about this reliability — packets sent with TCP are tracked so no data is lost or corrupted in transit. This is why file downloads do not become corrupted even if there are network hiccups. Of course, if the recipient is completely offline, your computer will give up and you will see an error message saying it can not communicate with the remote host.

UDP
UDP stands for User Datagram Protocol — a datagram is the same thing as a packet of information. The UDP protocol works similarly to TCP, but it throws all the error-checking stuff out. All the back-and-forth communication and deliverability guarantees slow things down.

When using UDP, packets are just sent to the recipient. The sender will not wait to make sure the recipient received the packet — it will just continue sending the next packets. If you are the recipient and you miss some UDP packets, too bad — you can not ask for those packets again. There is no guarantee you are getting all the packets and there is no way to ask for a packet again if you miss it, but losing all this overhead means the computers can communicate more quickly.

UDP is used when speed is desirable and error correction is not necessary. For example, UDP is frequently used for live broadcasts and online games.

This explanation is from: https://www.howtogeek.com/190014/htg-explains-what-is-the-difference-between-tcp-and-udp/

## Javascript new operator

- Create an empty object.
- Assign `obj.__proto__` to `ConstructorFn.prototype`
- Assign the object to `this`
- Execute function body
- return `this`

## CSS vertical align

- https://www.oxxostudio.tw/articles/201408/css-vertical-align.html
- https://www.oxxostudio.tw/articles/201502/css-vertical-align-7methods.html
  - 設定行高 ( line-height )
  - 添加偽元素
  - calc 動態計算
  - 使用表格或假裝表格
  - transform
  - 絕對定位
  - 使用 Flexbox

### vertical align with pseudo elements

https://codepen.io/bobwei/pen/ympoWw

```html
<div class="vertical-align container">
  <div class="vertical-align-element">
    center
  </div>
</div>
```

```css
.container {
  height: 300px;
  text-align: center;
  background-color: red;
}

.vertical-align::before {
  content: '';
  width: 0;
  height: 100%;
  display: inline-block;
  vertical-align: middle;
}

.vertical-align-element {
  display: inline-block;
}
```

## Javascript Prototype

- http://dmitrysoshnikov.com/ecmascript/javascript-the-core/

<img height="600" src="assets/constructor-proto-chain.png">

## React vs Vue

|           | React                                               | Vue                                                    |
| --------- | --------------------------------------------------- | ------------------------------------------------------ |
| summary   | 函數式編程、易於組合、資料流清晰，適用於大型場景    | 簡單易懂、容易上手                                     |
| data flow | 單向資料流、數據不可變，故資料較清晰、具可預測性    | 資料劫持以監聽變化，修改物件屬性即可反應變化，易於上手 |
| principle | composition of components, designed for composition |                                                        |

### Composition of components

- Higher Order Function
- Hooks
- Render Props

All of above help easier to separate concerns and having abstraction.
