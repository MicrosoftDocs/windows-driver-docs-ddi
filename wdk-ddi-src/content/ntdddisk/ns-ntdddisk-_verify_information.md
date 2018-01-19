---
UID: NS:ntdddisk._VERIFY_INFORMATION
title: _VERIFY_INFORMATION
author: windows-driver-content
description: The VERIFY_INFORMATION structure provides information used to verify the existence of a disk extent.
old-location: storage\verify_information.htm
old-project: storage
ms.assetid: 7bb5c2ff-9bdb-4958-b290-9edb18d02668
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _VERIFY_INFORMATION, VERIFY_INFORMATION, *PVERIFY_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VERIFY_INFORMATION
req.alt-loc: ntdddisk.h
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
req.typenames: VERIFY_INFORMATION, *PVERIFY_INFORMATION
---

# _VERIFY_INFORMATION structure



## -description
The VERIFY_INFORMATION structure provides information used to verify the existence of a disk extent.  



## -syntax

````
typedef struct _VERIFY_INFORMATION {
  LARGE_INTEGER StartingOffset;
  ULONG         Length;
} VERIFY_INFORMATION, *PVERIFY_INFORMATION;
````


## -struct-fields

### -field StartingOffset

Specifies the starting offset, in bytes, of the disk extent. 


### -field Length

Indicates the length, in bytes, of the disk extent. 


## -remarks
VERIFY_INFORMATION is the output buffer for the <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_verify.md">IOCTL_DISK_VERIFY</a> control code.


## -see-also
<dl>
<dt>
<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_verify.md">IOCTL_DISK_VERIFY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20VERIFY_INFORMATION structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

