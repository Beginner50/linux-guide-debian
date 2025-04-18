### Making Efficient Use of Browser Cache & Network IO
Since networking is a limiting resource for computers, caches have been developed in web browsers to minimize network I/O.

Therefore, it is critical for a web developer to know how to make efficient use of the browser cache using the following methods:

1) **Keep re-usable code in separate files:**
	Re-usable code should be kept in separate files since if they were to be bundled together with the file containing a web-page and that file were to change, then the whole file will have to re-fetched from the web server. However, if they were to be kept separate, then the cached version of the unchanged re-usable code will be used and only the web-page will be re-fetched.

2) **Using CDNs:** 
	CDNs (Content Delivery Networks) are servers spanning across the globe containing redundant data to reduce load time on browsers.

	Not only are CDNs offer much faster page load times than offering a file from your own server but since they are commonly used, a user might have already downloaded a common file from a CDN which is also used in your website. Therefore, a duplicate version of that file will not have to re-fetched from your web server and the cached version on their browser can be used instead.

3) **Lazy Loading of Resources:**
	Lazy loading defers loading of resources until they are needed.
	`loading="lazy"`

	For example, images that are not immediately visible on the screen can be loaded only when the user scrolls down to them. (Pagination)

4) **Compress Files before Transmission:**
	Compress HTML, CSS & JavaScript files using compression tools like Gzip before sending the to the client.

5) **Use WebSockets or Server-Sent Events for Real-Time Data**