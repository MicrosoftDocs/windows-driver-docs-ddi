---
UID: NS:61883._CIP_CANCEL_FRAME
title: "_CIP_CANCEL_FRAME"
author: windows-driver-content
description: The request cancels an attached frame buffer. A frame can be canceled while the stream is running.
old-location: ieee\cip_cancel_frame.htm
old-project: IEEE
ms.assetid: 952625D0-BA82-40C1-8EBF-8CD54C0E4C40
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: "*PCIP_CANCEL_FRAME, CIP_CANCEL_FRAME structure [Buses], _CIP_CANCEL_FRAME, CIP_CANCEL_FRAME, 61883/CIP_CANCEL_FRAME, PCIP_CANCEL_FRAME, IEEE.cip_cancel_frame, 61883/PCIP_CANCEL_FRAME, PCIP_CANCEL_FRAME structure pointer [Buses]"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 61883.h
req.include-header: 
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
-	61883.h
apiname:
-	CIP_CANCEL_FRAME
product: Windows
targetos: Windows
req.typenames: CIP_CANCEL_FRAME, *PCIP_CANCEL_FRAME
---

# _CIP_CANCEL_FRAME structure


## -description


This structure is the input buffer in a cancel frame request. The request cancels an attached frame buffer. A frame can be canceled while the stream is running. If the canceled frame has already been sent, the protocol driver sets a status of STATUS_NOT_FOUND.


## -syntax


````
typedef struct _CIP_CANCEL_FRAME {
  HANDLE     hConnect;
  PCIP_FRAME Frame;
} CIP_CANCEL_FRAME, *PCIP_CANCEL_FRAME;
````


## -struct-fields




### -field hConnect

A handle to a connection.


### -field Frame

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537045">CIP_FRAME</a> structure that contains information about the frame to cancel.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20CIP_CANCEL_FRAME structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

