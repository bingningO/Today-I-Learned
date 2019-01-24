need to set url as a param in url, need to encode & decode the url

1. if there is just some simple url, like **https://www.google.com/?a=1234**, Sprintboot can automately encode and decode the url for u

2. if the url is something like **https://www.google.com/?a=1234&b=234**, as the whole post url is like **http://localhost:8080/COS/web/eleme/testtest?name=bing&url=https://www.google.com/?a=1234&b=234**

as the Sprint don't know *&b=234* is the param of google.com or localhost:8888, so in Javascript(Frontend) should use *encodeURIComponent()* to encode the URL

and at the Backend u can directly get the original url 
