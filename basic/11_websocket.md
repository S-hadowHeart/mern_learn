# WebSockets

## Introduction

**WebSockets** are a communication technology that enables **real-time interaction** between a web browser (client) and a server.

Think of WebSockets as a **permanent open connection** between the browser and the server.
Unlike traditional web communication (which requires refreshing or repeated requests), WebSockets allow **instant data exchange without reloading the page**.

With WebSockets, developers can build:

* Chat applications
* Live notifications
* Real-time dashboards
* Online gaming systems
* Live data feeds (stocks, sports scores)

---

# Transmission Modes

Before understanding WebSockets, you need to understand **Transmission Modes**.

Transmission modes refer to the **direction of data flow** between two communication devices in a network.

There are three types:

---

## 1. Simplex

* Data flows in **one direction only**
* One device sends, the other only receives

Example:

* Keyboard → Computer
* TV broadcast

---

## 2. Half-Duplex

* Data flows in **both directions**
* But **only one direction at a time**

Example:

* Walkie-talkie
  (You speak, then the other person speaks)

---

## 3. Full-Duplex

* Data flows in **both directions simultaneously**

Example:

* Phone call
  (Both people can talk at the same time)

👉 **WebSockets use Full-Duplex communication**

---

# What is a WebSocket?

A **WebSocket** is a communication protocol that enables:

* **Full-duplex**
* **Bidirectional**
* **Persistent connection**
* **Real-time data transfer**

between a client and a server.

---
<img width="800" height="480" alt="image" src="https://github.com/user-attachments/assets/14659bb5-ed46-4060-afcb-1a090a669484" />

## WebSockets vs HTTP

### HTTP

* Unidirectional (client → server → response)
* Stateless
* Request–Response model
* Connection closes after response

### WebSockets

* Bidirectional
* Stateful (connection stays open)
* Real-time communication
* No need for repeated requests

---

# Why Were WebSockets Created?

Traditional HTTP works like this:

1. Client sends request
2. Server responds
3. Connection closes

This works well for:

* Static websites
* Basic forms
* Standard API calls

But it is **not suitable for real-time applications**.

---

## Problem Before WebSockets

To simulate real-time communication, developers used:

### 1. Polling

Client repeatedly sends requests to check for updates.

Problem:

* High server load
* Wasted bandwidth
* Slow response

### 2. Long Polling

Server keeps request open until new data is available.

Problem:

* Still inefficient
* Complex to manage
* Increased resource usage

---

## Solution: WebSockets

WebSockets:

* Create a **single persistent connection**
* Keep it open
* Allow data to flow in both directions anytime
* Reduce repeated requests
* Reduce server load

---

# How WebSockets Work (Simple Flow)

1. Client sends a special HTTP request (WebSocket handshake)
2. Server upgrades connection to WebSocket
3. Connection stays open
4. Both sides send data anytime

---

# Advantages of WebSockets

## 1. Real-Time Communication

Instant updates without refreshing the page.

## 2. Reduced Network Overhead

No repeated HTTP headers for every request.

## 3. Scalability

Handles many real-time users efficiently.

## 4. Reduced Server Load

No constant polling requests.

## 5. Flexibility

Can send text, JSON, binary data.

## 6. Security

Supports secure connections using:

```
wss://
```

(Secure WebSocket – like HTTPS)

---

# Disadvantages of WebSockets

## 1. Browser Compatibility

Older browsers may not fully support WebSockets.

## 2. Firewall & Proxy Issues

Some corporate firewalls block WebSocket connections.

## 3. Server Resource Usage

Persistent connections consume memory and resources.

## 4. More Complex Implementation

Harder than simple HTTP APIs.

---

# WebSocket URL Structure

Normal HTTP:

```
http://example.com
https://example.com
```

WebSocket:

```
ws://example.com
wss://example.com
```

* `ws` → WebSocket
* `wss` → Secure WebSocket

---

# Simple JavaScript Example

```javascript
// Create connection
const socket = new WebSocket("ws://localhost:3000");

// Connection opened
socket.onopen = function() {
  console.log("Connected to server");
  socket.send("Hello Server!");
};

// Receiving message
socket.onmessage = function(event) {
  console.log("Received:", event.data);
};

// Connection closed
socket.onclose = function() {
  console.log("Connection closed");
};
```

---

# Where WebSockets Are Used

* Live chat applications
* Online multiplayer games
* Real-time trading platforms
* Live sports updates
* Notification systems
* Collaborative tools (like Google Docs)

---

# Summary

* WebSockets enable **full-duplex, real-time communication**
* They solve the limitations of HTTP for real-time apps
* They reduce server load compared to polling
* Ideal for interactive web applications

---
