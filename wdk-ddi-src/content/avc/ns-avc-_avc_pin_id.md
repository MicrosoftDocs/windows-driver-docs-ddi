---
UID: NS:avc._AVC_PIN_ID
title: "_AVC_PIN_ID"
author: windows-driver-content
description: The AVC_PIN_ID structure describes a pin on a subunit.
old-location: stream\avc_pin_id.htm
old-project: stream
ms.assetid: 0341b1c4-a050-45f4-b9fc-b28b6a8af75d
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: "*PAVC_PIN_ID, PAVC_PIN_ID, stream.avc_pin_id, AVC_PIN_ID, _AVC_PIN_ID, avcref_28e8a7a5-a90b-4e1b-ad4c-1a1ccbc405c5.xml, AVC_PIN_ID structure [Streaming Media Devices], avc/PAVC_PIN_ID, avc/AVC_PIN_ID, PAVC_PIN_ID structure pointer [Streaming Media Devices]"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	avc.h
apiname:
-	AVC_PIN_ID
product: Windows
targetos: Windows
req.typenames: "*PAVC_PIN_ID, AVC_PIN_ID"
---

# _AVC_PIN_ID structure


## -description


The AVC_PIN_ID structure describes a pin on a subunit.


## -syntax


````
typedef struct _AVC_PIN_ID {
  ULONG PinId;
} AVC_PIN_ID, *PAVC_PIN_ID;
````


## -struct-fields




### -field PinId

Specifies the offset (or ID) of the pin.


## -remarks


This structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554148">AVC_FUNCTION_ACQUIRE</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff554169">AVC_FUNCTION_RELEASE</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff554149">AVC_FUNCTION_CLR_CONNECTINFO</a> function codes.

This structure is used only as a member inside the AVC_MULTIFUNC_IRB structure. It is not used by itself.

See <a href="https://msdn.microsoft.com/3b4ec139-ff01-40bd-8e29-92f554180585">How to Use Avc.sys</a> For information about building and sending an AV/C command.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554149">AVC_FUNCTION_CLR_CONNECTINFO</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554148">AVC_FUNCTION_ACQUIRE</a>

<a href="..\avc\ns-avc-_avc_multifunc_irb.md">AVC_MULTIFUNC_IRB</a>

<a href="..\avc\ne-avc-_tagavc_function.md">AVC_FUNCTION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554169">AVC_FUNCTION_RELEASE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVC_PIN_ID structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

