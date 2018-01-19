---
UID: NS:ntifs._FILE_GET_QUOTA_INFORMATION
title: _FILE_GET_QUOTA_INFORMATION
author: windows-driver-content
description: The FILE_GET_QUOTA_INFORMATION structure is used to query for quota information.
old-location: ifsk\file_get_quota_information.htm
old-project: ifsk
ms.assetid: 4c4d57bd-28b3-4db3-a172-bc1a27dd10b2
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _FILE_GET_QUOTA_INFORMATION, FILE_GET_QUOTA_INFORMATION, *PFILE_GET_QUOTA_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FILE_GET_QUOTA_INFORMATION
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
req.typenames: FILE_GET_QUOTA_INFORMATION, *PFILE_GET_QUOTA_INFORMATION
---

# _FILE_GET_QUOTA_INFORMATION structure



## -description
The FILE_GET_QUOTA_INFORMATION structure is used to query for quota information. 



## -syntax

````
typedef struct _FILE_GET_QUOTA_INFORMATION {
  ULONG NextEntryOffset;
  ULONG SidLength;
  SID   Sid;
} FILE_GET_QUOTA_INFORMATION, *PFILE_GET_QUOTA_INFORMATION;
````


## -struct-fields

### -field NextEntryOffset

Offset, in bytes, of the next FILE_GET_QUOTA_INFORMATION-typed entry. This member is zero if no other entries follow this one. 


### -field SidLength

Length, in bytes, of the <b>Sid</b> member. 


### -field Sid

Security identifier (<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>) whose quota information is to be returned. 


## -remarks
The FILE_GET_QUOTA_INFORMATION structure is used to query for quota information. The quota information is returned in a <a href="..\ntifs\ns-ntifs-_file_quota_information.md">FILE_QUOTA_INFORMATION</a>-structured buffer. 

This structure must be aligned on a LONG (4-byte) boundary. 


## -see-also
<dl>
<dt>
<a href="..\ntifs\ns-ntifs-_file_quota_information.md">FILE_QUOTA_INFORMATION</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-iocheckquotabuffervalidity.md">IoCheckQuotaBufferValidity</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549293">IRP_MJ_QUERY_QUOTA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549401">IRP_MJ_SET_QUOTA</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILE_GET_QUOTA_INFORMATION structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

