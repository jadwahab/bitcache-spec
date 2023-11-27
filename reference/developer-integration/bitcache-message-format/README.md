# BitCache Message Format

{% hint style="info" %}
BitCache messages are written to the BitCache channels in binary format. To make things easier, we have created libraries to serialise and deserialise BitCache messages [here](https://github.com/bitcache-tech/bitcache-message).
{% endhint %}

### Go Implementation

The [Go version of the BitCache Message Library](https://github.com/bitcache-tech/bitcache-message/tree/master/go) is designed for performance and reliability. It offers:

* **Strong Type Safety**: Go's strict type system helps prevent many types of errors at compile time, increasing the robustness of the serialization and deserialization processes.
* **High Performance**: Go's efficient memory management and concurrency model make the library particularly well-suited for high-throughput and low-latency applications.
* **Simplicity and Readability**: Go's straightforward syntax and language features allow for clear and maintainable code.

### Python Implementation

The [Python version of the BitCache Message Library](https://github.com/bitcache-tech/bitcache-message/tree/master/python) is intended to be simple and easy to understand:

* **Dependency free**: Uses only features present in the standard library that all Python developers should know or would benefit from knowing about.

### TypeScript/JavaScript Implementation

The [TypeScript/JavaScript version of the BitCache Message Library](https://github.com/bitcache-tech/bitcache-message/tree/master/ts) is tailored for flexibility and ease of integration in web applications:

* **Seamless Browser and Node.js Compatibility**: Designed to work effortlessly across server-side (Node.js) and client-side (browser) environments.
* **TypeScript Support**: Leverages TypeScript's static typing for enhanced code quality and maintainability in JavaScript-based projects.
* **Easy Integration with JavaScript Ecosystems**: The library can be effortlessly integrated with modern web development tools and frameworks, making it a versatile choice for web developers.



## More information

You can find more details regarding the message specification on the next page.
