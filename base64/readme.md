# Base64 Encode/Decode for ILE RPG
This is the source code for a service program written in ILE RPG for performing Base64 Encode/Decode on an iSeries system.  

Unfortunately, I do not have any documentation or sample code for calling these routines at this time, but I may post some later.   

The code will only work on an EBCDIC system. If you want to do the same thing in VARPG or another ASCII-based version of RPG, you will have to modify the base64 tables. This won't be a problem on an iSeries system, of course.   

Base64 is part of the MIME standard. For more information, please see section 6.8 of RFC 2045.   
