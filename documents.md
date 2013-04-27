# Document meta-data vs File meta-data in a document management application.

Meta data is information associated with a file.  Meta-data is information associated with a document.  So, what is the difference?  Let's look at the difference between the words document and file.

From http://www.merriam-webster.com

* Document:  a writing conveying information

* File: a complete collection of data (as text or a program) treated by a computer as a unit especially for purposes of input and output

So, just as a document's purpose is to convey information, document meta-data conveys information about the contents of a document.  File meta-data refers to information regarding the file itself.

**Examples**

* File name - name of data record used to open, save, or transfer a file by a computer; used by computers and computer programs
* Document title - name used to refer to a collection of information; used by people


* Last modified date - date a data record was last changed on a computer storage unit; could be the result of moving or renaming a file and not the result of a change to the file contents
* Revision date - date of last change of the information contained within a file



**Prior art:**

* [Google Drive - Files](https://developers.google.com/drive/v2/reference/files)
* [Google Drive - Manage File Metadata](https://developers.google.com/drive/v2/reference/files)
* [Dropbox REST API](https://www.dropbox.com/developers/core/api#metadata)

## How should an application handle document and file meta-data?

* The mechanisms for document and file meta-data should be distinct and separate

* File meta-data should be handled by HTTP headers.

* Document meta-data should be handled in much the way file transfer is handled.  By transferring a file containing the document meta-data to the client or server via a [RESTful](http://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm) mechanism.

 
  







