---
UID: NS:ntifs._FILE_LEVEL_TRIM_RANGE
title: _FILE_LEVEL_TRIM_RANGE
author: windows-driver-content
description: Contains the offset and length of a trim range for a file.
old-location: ifsk\file_level_trim_range.htm
old-project: ifsk
ms.assetid: C74E90C5-9876-4CD1-B9A7-1B32A6AAB474
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _FILE_LEVEL_TRIM_RANGE, FILE_LEVEL_TRIM_RANGE, *PFILE_LEVEL_TRIM_RANGE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FILE_LEVEL_TRIM_RANGE
req.alt-loc: ntifs.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: FILE_LEVEL_TRIM_RANGE, *PFILE_LEVEL_TRIM_RANGE
---

# _FILE_LEVEL_TRIM_RANGE structure



## -description
Contains the offset and length of a trim range for a file.



## -syntax

````
typedef struct _FILE_LEVEL_TRIM_RANGE {
  ULONGLONG Offset;
  ULONGLONG Length;
} FILE_LEVEL_TRIM_RANGE, *PFILE_LEVEL_TRIM_RANGE;
````


## -struct-fields

### -field Offset

Byte offset from the front of the given file to trim at.


### -field Length

Length in bytes to trim from the given offset.


## -remarks
Due to alignment requirements, the file system may reduce the of the the trim range to a multiple of <b>PAGE_SIZE</b> &lt;= <b>Length</b>. Also, <b>Offset</b> will be adjusted to the next page boundary if its initial value is not on page boundary.


## -see-also
<dl>
<dt>
<a href="..\ntifs\ns-ntifs-_file_level_trim.md">FILE_LEVEL_TRIM</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILE_LEVEL_TRIM_RANGE structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

