---
UID: NS:fltuserstructures._FILTER_MESSAGE_HEADER
title: "_FILTER_MESSAGE_HEADER"
author: windows-driver-content
description: The FILTER_MESSAGE_HEADER structure contains message header information.
old-location: ifsk\filter_message_header.htm
old-project: ifsk
ms.assetid: 294e5475-3aca-4758-87ed-07892a910b4f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PFILTER_MESSAGE_HEADER, FILTER_MESSAGE_HEADER, FILTER_MESSAGE_HEADER structure [Installable File System Drivers], FltSystemStructures_80f5d30b-5507-45c8-b399-6fa816ba9232.xml, PFILTER_MESSAGE_HEADER, PFILTER_MESSAGE_HEADER structure pointer [Installable File System Drivers], _FILTER_MESSAGE_HEADER, fltuserstructures/FILTER_MESSAGE_HEADER, fltuserstructures/PFILTER_MESSAGE_HEADER, ifsk.filter_message_header"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fltuserstructures.h
api_name:
-	FILTER_MESSAGE_HEADER
product: Windows
targetos: Windows
req.typenames: FILTER_MESSAGE_HEADER, *PFILTER_MESSAGE_HEADER
---

# _FILTER_MESSAGE_HEADER structure


## -description


The FILTER_MESSAGE_HEADER structure contains message header information. 


## -syntax


````
typedef struct _FILTER_MESSAGE_HEADER {
  ULONG     ReplyLength;
  ULONGLONG MessageId;
} FILTER_MESSAGE_HEADER, *PFILTER_MESSAGE_HEADER;
````


## -struct-fields




### -field ReplyLength

On output from <a href="https://msdn.microsoft.com/library/windows/hardware/ff540506">FilterGetMessage</a>, this field receives the length, in bytes, of the expected reply, including the FILTER_REPLY_HEADER header. Set to zero if no reply is expected. 


### -field MessageId

On output from <a href="https://msdn.microsoft.com/library/windows/hardware/ff540506">FilterGetMessage</a>, this field receives the unique identifier (ID) for the message sent by the kernel-mode driver. If the application replies to the message, it must set this ID in the <b>MessageId</b> field of the FILTER_REPLY_HEADER header in the reply. 


## -remarks



To receive messages from a kernel-mode minifilter, a user-mode application typically defines a custom message structure. This structure typically consists of this header structure, followed by an application-defined structure to hold the actual message data. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540506">FilterGetMessage</a>



<a href="..\fltuserstructures\ns-fltuserstructures-_filter_reply_header.md">FILTER_REPLY_HEADER</a>



 

 


