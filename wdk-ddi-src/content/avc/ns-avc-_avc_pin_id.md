---
UID: NS:avc._AVC_PIN_ID
title: _AVC_PIN_ID (avc.h)
description: The AVC_PIN_ID structure describes a pin on a subunit.
old-location: stream\avc_pin_id.htm
tech.root: stream
ms.assetid: 0341b1c4-a050-45f4-b9fc-b28b6a8af75d
ms.date: 04/23/2018
ms.keywords: "*PAVC_PIN_ID, AVC_PIN_ID, AVC_PIN_ID structure [Streaming Media Devices], PAVC_PIN_ID, PAVC_PIN_ID structure pointer [Streaming Media Devices], _AVC_PIN_ID, avc/AVC_PIN_ID, avc/PAVC_PIN_ID, avcref_28e8a7a5-a90b-4e1b-ad4c-1a1ccbc405c5.xml, stream.avc_pin_id"
ms.topic: struct
f1_keywords:
 - "avc/AVC_PIN_ID"
req.header: avc.h
req.include-header: Avc.h
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
- avc.h
api_name:
- AVC_PIN_ID
product:
- Windows
targetos: Windows
req.typenames: AVC_PIN_ID, *PAVC_PIN_ID
---

# _AVC_PIN_ID structure


## -description


The AVC_PIN_ID structure describes a pin on a subunit.


## -struct-fields




### -field PinId

Specifies the offset (or ID) of the pin.


## -remarks



This structure is used with the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avc-function-acquire">AVC_FUNCTION_ACQUIRE</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avc-function-release">AVC_FUNCTION_RELEASE</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avc-function-clr-connectinfo">AVC_FUNCTION_CLR_CONNECTINFO</a> function codes.

This structure is used only as a member inside the AVC_MULTIFUNC_IRB structure. It is not used by itself.

See <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/using-avc-sys">How to Use Avc.sys</a> For information about building and sending an AV/C command.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/avc/ne-avc-_tagavc_function">AVC_FUNCTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avc-function-acquire">AVC_FUNCTION_ACQUIRE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avc-function-clr-connectinfo">AVC_FUNCTION_CLR_CONNECTINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avc-function-release">AVC_FUNCTION_RELEASE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/avc/ns-avc-_avc_multifunc_irb">AVC_MULTIFUNC_IRB</a>
 

 


