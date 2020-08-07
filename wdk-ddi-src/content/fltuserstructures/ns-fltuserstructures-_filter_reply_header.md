---
UID: NS:fltuserstructures._FILTER_REPLY_HEADER
title: _FILTER_REPLY_HEADER (fltuserstructures.h)
description: The FILTER_REPLY_HEADER structure contains message reply header information.
old-location: ifsk\filter_reply_header.htm
tech.root: ifsk
ms.assetid: 2765ccb0-3389-4962-8a7d-8080cb3c8806
ms.date: 04/16/2018
keywords: ["FILTER_REPLY_HEADER structure"]
ms.keywords: "*PFILTER_REPLY_HEADER, FILTER_REPLY_HEADER, FILTER_REPLY_HEADER structure [Installable File System Drivers], FltSystemStructures_93e9fad2-e89d-40af-8614-c09a51f07e7b.xml, PFILTER_REPLY_HEADER, PFILTER_REPLY_HEADER structure pointer [Installable File System Drivers], _FILTER_REPLY_HEADER, fltuserstructures/FILTER_REPLY_HEADER, fltuserstructures/PFILTER_REPLY_HEADER, ifsk.filter_reply_header"
f1_keywords:
 - "fltuserstructures/FILTER_REPLY_HEADER"
 - "FILTER_REPLY_HEADER"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- fltuserstructures.h
api_name:
- FILTER_REPLY_HEADER
targetos: Windows
req.typenames: FILTER_REPLY_HEADER, *PFILTER_REPLY_HEADER
---

# _FILTER_REPLY_HEADER structure


## -description


The FILTER_REPLY_HEADER structure contains message reply header information. 


## -struct-fields




### -field Status

Status value to be returned for the original message. 


### -field MessageId

Unique ID received in the <b>MessageId</b> field of the original message. 


## -remarks



This structure is allocated by a user-mode application. It is a container for a reply that the application sends in response to a message received from a kernel-mode minifilter or minifilter instance. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltuserstructures/ns-fltuserstructures-_filter_message_header">FILTER_MESSAGE_HEADER</a>



<a href="https://docs.microsoft.com/windows/win32/api/fltuser/nf-fltuser-filterreplymessage">FilterReplyMessage</a>
 

 

