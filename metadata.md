# What is meta data?

Meta data is information associated with a file.  HTTP headers such as 
Content-Type and Content-Length are one kind meta data: strings that
do not contain a carriage return (CR) or line feed (LF).  Other examples 
of meta data are XML documents and JSON documents.

**Prior art:**

* [Google Drive - Files](https://developers.google.com/drive/v2/reference/files)
* [Google Drive - Manage File Metadata](https://developers.google.com/drive/v2/reference/files)
* [Dropbox REST API](https://www.dropbox.com/developers/core/api#metadata)

## Headers or Documents?

Should meta data be passed as headers or documents?  Both for different reasons.

Headers should be limited to meta data sent between the server and
the client in order to facilate the correct handling of the file.
Examples would be ETag or Expires headers used by the client to determine
if a local copy of a file should be downloaded or not. Common headers
are listed in [RFC4229](http://tools.ietf.org/html/rfc4229).
 
Documents should be used by an application to track information about 
the file which is application specific or not relevant to how the client
or server handles the file.  Examples of data contained in
a document would be an abstract of the file contents, revision dates,
and the authors of a file.

Servers SHOULD send headers to clients whenever a GET
or HEAD request is made for a file.  Clients SHOULD be able to set
or update headers by including them in a POST or PUT request. 
`Should all headers be editable by the client?  Probably not.`  

A server SHOULD only send a document upon request.  A server
that supports application documents SHOULD provide fixed URLs for creating,
updating, deleting, and getting these documents.