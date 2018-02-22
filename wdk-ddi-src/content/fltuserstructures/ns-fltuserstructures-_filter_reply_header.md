---
UID: NS:fltuserstructures._FILTER_REPLY_HEADER
title: "_FILTER_REPLY_HEADER"
author: windows-driver-content
description: The FILTER_REPLY_HEADER structure contains message reply header information.
old-location: ifsk\filter_reply_header.htm
old-project: ifsk
ms.assetid: 2765ccb0-3389-4962-8a7d-8080cb3c8806
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FILTER_REPLY_HEADER, PFILTER_REPLY_HEADER structure pointer [Installable File System Drivers], PFILTER_REPLY_HEADER, ifsk.filter_reply_header, *PFILTER_REPLY_HEADER, _FILTER_REPLY_HEADER, FltSystemStructures_93e9fad2-e89d-40af-8614-c09a51f07e7b.xml, FILTER_REPLY_HEADER structure [Installable File System Drivers], fltuserstructures/FILTER_REPLY_HEADER, fltuserstructures/PFILTER_REPLY_HEADER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fltuserstructures.h
req.include-header: FltUser.h, Fltkernel.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	fltuserstructures.h
apiname:
-	FILTER_REPLY_HEADER
product: Windows
targetos: Windows
req.typenames: FILTER_REPLY_HEADER, *PFILTER_REPLY_HEADER
---

# _FILTER_REPLY_HEADER structure


## -description


The FILTER_REPLY_HEADER structure contains message reply header information. 


## -syntax


````
typedef struct _FILTER_REPLY_HEADER {
  NTSTATUS  Status;
  ULONGLONG MessageId;
} FILTER_REPLY_HEADER, *PFILTER_REPLY_HEADER;
````


## -struct-fields




### -field Status

Status value to be returned for the original message. 


### -field MessageId

Unique ID received in the <b>MessageId</b> field of the original message. 


## -remarks



This structure is allocated by a user-mode application. It is a container for a reply that the application sends in response to a message received from a kernel-mode minifilter or minifilter instance. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541508">FilterReplyMessage</a>



<a href="..\fltuserstructures\ns-fltuserstructures-_filter_message_header.md">FILTER_MESSAGE_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILTER_REPLY_HEADER structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

