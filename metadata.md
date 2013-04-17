# What is meta data?

Meta data is information associated with a file.  HTTP headers such as 
Content-Type and Content-Length are one kind meta data: strings that
do not contain a carriage return (CR) or line feed (LF).  Other examples 
of meta data are XML documents and JSON documents.

**Prior art:**

* [Google Drive - Files](https://developers.google.com/drive/v2/reference/files)
* [Google Drive - Manage File Metadata](https://developers.google.com/drive/v2/reference/files)
* [Dropbox REST API](https://www.dropbox.com/developers/core/api#metadata)

# What meta data should tusio be concerned with?

  The tus-resumable-upload-protocol should limit itself to meta data related to proper file handling
  such as the headers Content-Length and Content-Disposition.  A tusio server SHOULD be configurable
  to handle other headers such as those listed in [RFC4229](http://tools.ietf.org/html/rfc4229).
  
  Any associated data beyond that necessary to handle file upload and download SHOULD be handled by 
  applications that utilize the tus-resumable-upload-protocol.
  
  When an initial request for a file upload is made, the server response SHOULD include a list of 
  accepted headers using the Access-Control-Allow-Headers.
  
  A tusio server MUST accept at the minimum Content-Type and Content-Length headers.
  
  Example:
 
``` 
  POST /files/24e533e02ec3bc40c387f1a0e460e216/documents HTTP/1.1
  Host: tus.example.com
  Content-Length: 100
  Content-Range: bytes 0-99/100
  Access-Control-Allow-Headers: Content-Type, Etag, Content-Length, Content-Disposition
```
  

