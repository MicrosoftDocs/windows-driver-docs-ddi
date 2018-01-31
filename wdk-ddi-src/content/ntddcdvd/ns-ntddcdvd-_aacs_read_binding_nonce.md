---
UID: NS:ntddcdvd._AACS_READ_BINDING_NONCE
title: "_AACS_READ_BINDING_NONCE"
author: windows-driver-content
description: The AACS_READ_BINDING_NONCE structure is a wrapper for the Authentication Grant Identifier (AGID) and logical block address (LBA)/length pair that are required to read a nonce.
old-location: storage\aacs_read_binding_nonce.htm
old-project: storage
ms.assetid: 5d017896-bb83-4ea3-9d28-b774213f86e9
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ntddcdvd/PAACS_READ_BINDING_NONCE, PAACS_READ_BINDING_NONCE, AACS_READ_BINDING_NONCE, structs-DVD_bc4b150f-5fa2-4c8d-b8fa-d3c3bf1c8639.xml, PAACS_READ_BINDING_NONCE structure pointer [Storage Devices], AACS_READ_BINDING_NONCE structure [Storage Devices], *PAACS_READ_BINDING_NONCE, _AACS_READ_BINDING_NONCE, ntddcdvd/AACS_READ_BINDING_NONCE, storage.aacs_read_binding_nonce
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddcdvd.h
apiname:
-	AACS_READ_BINDING_NONCE
product: Windows
targetos: Windows
req.typenames: AACS_READ_BINDING_NONCE, *PAACS_READ_BINDING_NONCE
---

# _AACS_READ_BINDING_NONCE structure


## -description


The AACS_READ_BINDING_NONCE structure is a wrapper for the Authentication Grant Identifier (AGID) and logical block address (LBA)/length pair that are required to read a nonce.


## -syntax


````
typedef struct _AACS_READ_BINDING_NONCE {
  DVD_SESSION_ID SessionId;
  ULONG          NumberOfSectors;
  ULONGLONG      StartLba;
  union {
    HANDLE    Handle;
    ULONGLONG ForceStructureLengthToMatch64bit;
  };
} AACS_READ_BINDING_NONCE, *PAACS_READ_BINDING_NONCE;
````


## -struct-fields




#### - Handle

The file handle. Callers of IOCTL_AACS_READ_BINDING_NONCE that use file system support can set this member to a file handle. If the caller does not use file system support, this member must have a value of INVALID_HANDLE_VALUE.


#### - ForceStructureLengthToMatch64bit



#### - SessionId

A value of type DVD_SESSION_ID that specifies an AGID. The client obtains this value by a successful call to IOCTL_AACS_START_SESSION.


#### - NumberOfSectors

The number of sectors in the area for which the binding nonce is retrieved. To request the nonce for a file, the caller of IOCTL_AACS_READ_BINDING_NONCE must set this member to MAXULONGLONG.


#### - StartLba

The starting logical block address of the area for which the binding nonce is retrieved. To request the nonce for a file, the caller of <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_generate_binding_nonce.md">IOCTL_AACS_GENERATE_BINDING_NONCE</a> or <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_read_binding_nonce.md">IOCTL_AACS_READ_BINDING_NONCE</a> must set this member to MAXULONGLONG.


## -remarks


Clients retrieve the binding nonce with an <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_generate_binding_nonce.md">IOCTL_AACS_GENERATE_BINDING_NONCE</a> request or an <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_read_binding_nonce.md">IOCTL_AACS_READ_BINDING_NONCE</a> request.



## -see-also

<a href="..\ntddcdvd\ns-ntddcdvd-_aacs_binding_nonce.md">AACS_BINDING_NONCE</a>

<a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_generate_binding_nonce.md">IOCTL_AACS_GENERATE_BINDING_NONCE</a>

<a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_read_binding_nonce.md">IOCTL_AACS_READ_BINDING_NONCE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AACS_READ_BINDING_NONCE structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

