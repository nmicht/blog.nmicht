---
layout: post
title: Extensible Priorities
tags: computer-networks
---

Extensible priorities in HTTP/1.1 and HTTP/2 refer to mechanisms that allow clients to specify the importance of different resources being requested from a server, which helps in optimizing the loading of web pages by prioritizing critical resources.

## HTTP/1.1 Priorities

In HTTP/1.1, prioritization is relatively simple and not as well-defined as in HTTP/2. Clients, such as web browsers, can make multiple concurrent requests to a server, and servers typically handle these requests in the order they are received. However, browsers and clients can influence prioritization through:

1. **Concurrent Connections**: Browsers open multiple connections to the same server to fetch resources in parallel.
2. **Request Order**: Browsers often issue requests in a specific order to prioritize certain resources (e.g., HTML and CSS files) before others (e.g., images).

## HTTP/2 Priorities

HTTP/2 introduces a more sophisticated and flexible priority scheme, which allows clients to express more granular priority information for resource requests. This scheme includes:

1. **Streams**: Each request/response exchange in HTTP/2 happens over a stream. Streams can be assigned dependencies and weights.
2. **Stream Dependencies**: A stream can depend on another stream. This creates a dependency tree, where a child stream's priority is influenced by its parent stream.
3. **Weights**: Each stream has a weight (from 1 to 256) that indicates its relative priority compared to other streams with the same parent.

## Extensible Prioritization Scheme

The extensible prioritization scheme aims to improve and standardize how priorities are communicated and handled in HTTP. This is especially relevant for HTTP/2 and HTTP/3, where more complex prioritization is possible and necessary due to the multiplexing of streams.

### Goals of Extensible Prioritization

1. **Flexibility**: Allow clients to express detailed priorities based on their needs.
2. **Interoperability**: Standardize how priorities are communicated between clients and servers to ensure consistent behavior.
3. **Efficiency**: Optimize resource loading to improve user experience.

### Components of Extensible Prioritization

1. **Priority Headers**: HTTP headers used to specify the priority of a request. The `Priority` header can convey details such as urgency and incremental importance.
   - **Urgency**: Indicates the importance of a response. Lower values mean higher urgency.
   - **Incremental**: Indicates whether the response can be delivered incrementally (e.g., progressive images).

2. **Priority Settings in HTTP/2**: Enhancements to the existing HTTP/2 priority scheme to support more flexible and extensible priorities.

## Example of Prioritization in HTTP/2

Consider a web page that includes multiple resources such as HTML, CSS, JavaScript, and images. The browser might prioritize these resources as follows:

1. **HTML (Highest Priority)**: The main HTML document is critical and should be loaded first.
2. **CSS (High Priority)**: CSS files are necessary for rendering the page correctly and should be loaded immediately after the HTML.
3. **JavaScript (Medium Priority)**: JavaScript files are important but can be loaded after the essential rendering resources.
4. **Images (Lower Priority)**: Images are often less critical for the initial render and can be loaded with lower priority.

Using HTTP/2 prioritization, the browser can create a dependency tree and assign weights to these resources to ensure they are loaded in the optimal order.

## Example from a Big Company: Google Chrome

Google Chrome implements HTTP/2 prioritization to enhance web performance. Chrome assigns priorities to resources based on their type and importance to the page's rendering. By leveraging HTTP/2's prioritization scheme, Chrome ensures that critical resources like HTML, CSS, and JavaScript are loaded before less critical resources like images and third-party scripts, improving page load times and user experience.

## Conclusion

Extensible priorities in HTTP/1.1 and HTTP/2 are mechanisms that allow clients to specify the importance of different resources, optimizing the loading process of web pages. While HTTP/1.1 has basic prioritization through concurrent connections and request order, HTTP/2 introduces a more detailed and flexible priority scheme with stream dependencies and weights. The extensible prioritization scheme further enhances this by standardizing priority communication and improving efficiency.

For more detailed information, you can explore:
- [HTTP/2 Specification - Prioritization](https://tools.ietf.org/html/rfc7540#section-5.3)
- [Extensible Prioritization Scheme for HTTP](https://datatracker.ietf.org/doc/draft-ietf-httpbis-priority/)


_Disclaimer: This post was generated with the help of ChatGPT_