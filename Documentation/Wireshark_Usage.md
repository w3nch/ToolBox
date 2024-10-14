#tool
## 1. Filter by TCP Port

``` wireshark
tcp.port == <PORT_NUMBER>
```
- Filters packets based on a specific TCP port. Replace `<PORT_NUMBER>` with the desired port (e.g., `80` for HTTP or `443` for HTTPS) to focus on relevant traffic.
## 2. HTTP Authentication Header

``` wireshark
http.authheader
```
- Captures packets that include the HTTP authentication header. Useful for identifying requests that contain authentication tokens.
## 3. HTTP Response Code

``` wireshark
http.response.code == 200
```
- Filters for HTTP responses with a status code of `200`, indicating a successful request. This helps in verifying that the server successfully processed the request.
## 4. HTTP Request Methods

``` wireshark
http.request.method == "GET" || http.request.method == "POST"
```
- Captures packets that utilize either the `GET` or `POST` HTTP request methods. This is essential for monitoring user-initiated requests and data submissions.
## 5. Filter by URI 

``` wireshark
http.request.uri contains "admin"
```
- Identifies requests that attempt to access URLs containing the word "admin". This can help in detecting unauthorized access attempts to admin panels.
## 6. Frame Matching

``` wireshark
frame matches "desktop"
```
- Filters frames that match the string "desktop", potentially used to capture Windows usernames in the network traffic. This can aid in user identification during analysis.
