---
UID: NS:usbfnbase._USBFN_PIPE_INFORMATION
title: "_USBFN_PIPE_INFORMATION"
author: windows-driver-content
description: Describes attributes of a pipe associated with an endpoint on a specific interface.
old-location: buses\usbfn_pipe_information.htm
old-project: usbref
ms.assetid: F8BBD279-3694-4559-83B3-9312EF4153C0
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUSBFN_PIPE_INFORMATION, PUSBFN_PIPE_INFORMATION, PUSBFN_PIPE_INFORMATION structure pointer [Buses], USBFN_PIPE_INFORMATION, USBFN_PIPE_INFORMATION structure [Buses], _USBFN_PIPE_INFORMATION, buses.usbfn_pipe_information, usbfnbase/PUSBFN_PIPE_INFORMATION, usbfnbase/USBFN_PIPE_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbfnbase.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbfnbase.h
api_name:
-	USBFN_PIPE_INFORMATION
product: Windows
targetos: Windows
req.typenames: USBFN_PIPE_INFORMATION, *PUSBFN_PIPE_INFORMATION
req.product: Windows 10 or later.
---

# _USBFN_PIPE_INFORMATION structure


## -description


Describes attributes of a pipe associated with an endpoint on a specific interface.


## -struct-fields




### -field EpDesc

Describes the endpoint descriptor in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539317">USB_ENDPOINT_DESCRIPTOR</a> structure.


### -field PipeId

The pipe identifier (ID).


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539317">USB_ENDPOINT_DESCRIPTOR</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBFN_PIPE_INFORMATION structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

