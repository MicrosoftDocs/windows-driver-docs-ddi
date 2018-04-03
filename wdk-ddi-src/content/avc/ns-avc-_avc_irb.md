---
UID: NS:avc._AVC_IRB
title: "_AVC_IRB"
author: windows-driver-content
description: The AVC_IRB structure is an I/O Request Block (IRB) header structure where a function number is stored.
old-location: stream\avc_irb.htm
old-project: stream
ms.assetid: 8798e152-6586-48d0-a8f6-2e861660dd62
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PAVC_IRB, AVC_IRB, AVC_IRB structure [Streaming Media Devices], PAVC_IRB, PAVC_IRB structure pointer [Streaming Media Devices], _AVC_IRB, avc/AVC_IRB, avc/PAVC_IRB, avcref_98d983db-d72a-4efd-9c8c-20dd17b674a0.xml, stream.avc_irb"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	avc.h
api_name:
-	AVC_IRB
product:
- Windows
targetos: Windows
req.typenames: AVC_IRB, *PAVC_IRB
---

# _AVC_IRB structure


## -description


The AVC_IRB structure is an I/O Request Block (IRB) header structure where a function number is stored.


## -syntax


````
typedef struct _AVC_IRB {
  AVC_FUNCTION Function;
} AVC_IRB, *PAVC_IRB;
````


## -struct-fields




### -field Function

Value from the AVC_FUNCTION enumeration specifying a function number.


## -remarks



This structure is included at the head of the AVC_COMMAND_IRB and AVC_MULTIFUNC_IRB structures. These structures represent the I/O request block (IRB) associated with specific types of AV/C functions. Each specific type of AV/C function is documented in IOCTL_AVC_CLASS.




## -see-also

<a href="..\avc\ne-avc-_tagavc_function.md">AVC_FUNCTION</a>



<a href="..\avc\ns-avc-_avc_command_irb.md">AVC_COMMAND_IRB</a>



<a href="..\avc\ni-avc-ioctl_avc_class.md">IOCTL_AVC_CLASS</a>



<a href="..\avc\ns-avc-_avc_multifunc_irb.md">AVC_MULTIFUNC_IRB</a>



 

 


