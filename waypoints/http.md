# HTTP

* [Material](https://github.com/turingschool/curriculum/blob/master/source/projects/http_yeah_you_know_me.markdown)

## Waypoints

[Example Video](https://vimeo.com/150717928)


* Recite the anatomy of a request and of a response, without any aid.
* Using `$ curl -i some-url` to send a request and print the response
  * View a redirect and note the status code and Location header (http://google.com will redirect you to http://www.google.com)
  * View an html body and note the `Content-Type` header
  * View a JSON body, and predict the `Content-Type` header (https://api.github.com will return JSON)
* Using the browser to make requests to your server, started with `$ nc -l 9292`, and typing in the response by hand
  * View a GET request that was sent from your browser, render this form, which has a `Content-Length` of 125

    ```html
    <form action='/lolwut' method='post'>
      <input type='textarea' name='omghi'></input>
      <input type='Submit'></input>
    </form>
    ```
  * Fill in the form you rendered for the above step and submit it to see a POST request. Predict the path, the `Content-Type`, and the body.
  * Set a cookie
    * Show that the cookie comes back on subsequent requests
    * Show that the cookie is set in the browser
  * Redirect the browser to http://turing.io
  * Serve HTML and have it interpreted correctly by the browser (eg `<strong>` tags get bolded)
  * Serve the same HTML, but change 1 header to so the browser displays it as plain text instead
