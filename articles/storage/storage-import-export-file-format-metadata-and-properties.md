---
title: Import-Export Service Metadata and Properties File Format | Microsoft Docs
description: Learn how to specify metadata and properties for one or more blobs that are part of an import or export job
author: muralikk
manager: syadav
editor: tysonn
services: storage
documentationcenter: ''

ms.assetid: 840364c6-d9a8-4b43-a9f3-f7441c625069
ms.service: storage
ms.workload: storage 
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 01/15/2017
ms.author: muralikk

---
# Import-Export Service Metadata and Properties File Format
You can specify metadata and properties for one or more blobs as part of an import job or an export job. To set metadata or properties for blobs being created as part of an import job, you provide a metadata or properties file on the hard drive containing the data to be imported. For an export job, metadata and properties are written to a metadata or properties file that is included on the hard drive returned to you.  
  
## Metadata File Format  
The format of a metadata file is as follows:  
  
```xml
<?xml version="1.0" encoding="UTF-8"?>  
<Metadata>  
[<metadata-name-1>metadata-value-1</metadata-name-1>]  
[<metadata-name-2>metadata-value-2</metadata-name-2>]  
. . .  
</Metadata>  
```
  
|XML Element|Type|Description|  
|-----------------|----------|-----------------|  
|`Metadata`|Root element|The root element of the metadata file.|  
|`metadata-name`|String|Optional. The XML element specifies the name of the metadata for the blob, and its value specifies the value of the metadata setting.|  
  
## Properties File Format  
The format of a properties file is as follows:  
  
```xml
<?xml version="1.0" encoding="UTF-8"?>  
<Properties>  
[<Last-Modified>date-time-value</Last-Modified>]  
[<Etag>etag</Etag>]  
[<Content-Length>size-in-bytes<Content-Length>]  
[<Content-Type>content-type</Content-Type>]  
[<Content-MD5>content-md5</Content-MD5>]  
[<Content-Encoding>content-encoding</Content-Encoding>]  
[<Content-Language>content-language</Content-Language>]  
[<Cache-Control>cache-control</Cache-Control>]  
</Properties>  
```
  
|XML Element|Type|Description|  
|-----------------|----------|-----------------|  
|`Properties`|Root element|The root element of the properties file.|  
|`Last-Modified`|String|Optional. The last-modified time for the blob. For export jobs only.|  
|`Etag`|String|Optional. The blob’s ETag value. For export jobs only.|  
|`Content-Length`|String|Optional. The size of the blob in bytes. For export jobs only.|  
|`Content-Type`|String|Optional. The content type of the blob.|  
|`Content-MD5`|String|Optional. The blob's MD5 hash.|  
|`Content-Encoding`|String|Optional. The blob's content encoding.|  
|`Content-Language`|String|Optional. The blob's content language.|  
|`Cache-Control`|String|Optional. The cache control string for the blob.|  
  
 See [Set Blob Properties](/rest/api/storageservices/fileservices/set-blob-properties), [Set Blob Metadata](/rest/api/storageservices/fileservices/set-blob-metadata), and [Setting and Retrieving Properties and Metadata for Blob Resources](/rest/api/storageservices/fileservices/setting-and-retrieving-properties-and-metadata-for-blob-resources) for detailed rules about setting blob metadata and properties.
