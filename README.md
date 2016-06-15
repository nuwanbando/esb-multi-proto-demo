#### This repository contains a ESB demonstration on FTP/JMS/HTTP support ####

The solutions architeture is as follows,

![alt text](https://github.com/nuwanbando/esb-multi-proto-demo/blob/master/sa/sa05252016.png "Solution Architecture")

```
//Copy MB-HOME/client-libs/* to a new folder in containers/esb/artifacts/mb-libs 
//Copy mysql-connector* to containers/dss/artifacts
//Navigate to containers/ dir and execute

$ docker-compose up -d

/*
 * This will start DSS / MB / DSS and deploy the samples
 * You can publish a payload from MB to "books" queue or 
 * post a payload via http endpoint
 */


```

```xml
//payload

   <book id="bk101">
      <author>Gambardella, Matthew</author>
      <title>XML Developer's Guide</title>
      <genre>Computer</genre>
      <price>44.95</price>
      <publish_date>2000-10-01</publish_date>
      <description>An in-depth look at creating applications 
      with XML.</description>
   </book>
```

```
//you can post like

POST /library/books HTTP/1.1
Host: docker.machine:8280
Content-Type: application/xml
Cache-Control: no-cache
Postman-Token: ec73edb4-fdea-6bb4-68b6-396254946328

&lt;book id="bk151"&gt;
      &lt;author&gt;Gambardella, Matthew&lt;/author&gt;
      &lt;title&gt;XML Developer's Guide&lt;/title&gt;
      &lt;genre&gt;Computer&lt;/genre&gt;
      &lt;price&gt;44.95&lt;/price&gt;
      &lt;publish_date&gt;2000-10-01&lt;/publish_date&gt;
      &lt;description&gt;An in-depth look at creating applications 
      with XML.&lt;/description&gt;
   &lt;/book&gt;

```

```
//you can get like

GET /library/books/bk101 HTTP/1.1
Host: docker.machine:8280
Cache-Control: no-cache
```

