---
UID: NS:usbfnbase._USBFN_PIPE_INFORMATION
title: "_USBFN_PIPE_INFORMATION" (usbfnbase.h)
description: Describes attributes of a pipe associated with an endpoint on a specific interface.
old-location: buses\usbfn_pipe_information.htm
tech.root: usbref
ms.assetid: F8BBD279-3694-4559-83B3-9312EF4153C0
ms.date: 05/07/2018
ms.keywords: "*PUSBFN_PIPE_INFORMATION, PUSBFN_PIPE_INFORMATION, PUSBFN_PIPE_INFORMATION structure pointer [Buses], USBFN_PIPE_INFORMATION, USBFN_PIPE_INFORMATION structure [Buses], _USBFN_PIPE_INFORMATION, buses.usbfn_pipe_information, usbfnbase/PUSBFN_PIPE_INFORMATION, usbfnbase/USBFN_PIPE_INFORMATION"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbfnbase.h
api_name:
-	USBFN_PIPE_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: USBFN_PIPE_INFORMATION, *PUSBFN_PIPE_INFORMATION
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
 

 

