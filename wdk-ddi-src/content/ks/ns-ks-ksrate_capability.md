---
UID: NS:ks.KSRATE_CAPABILITY
title: KSRATE_CAPABILITY
author: windows-driver-content
description: The client uses the KSRATE_CAPABILITY structure in a KSPROPERTY_STREAM_RATECAPABILITY property request.
old-location: stream\ksrate_capability.htm
old-project: stream
ms.assetid: 70866a87-0ebd-4230-9958-ace18116fa23
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: "*PKSRATE_CAPABILITY, ks-struct_4697e3ed-7ef5-4278-be5f-96083d755ab0.xml, ks/KSRATE_CAPABILITY, KSRATE_CAPABILITY structure [Streaming Media Devices], KSRATE_CAPABILITY, PKSRATE_CAPABILITY, PKSRATE_CAPABILITY structure pointer [Streaming Media Devices], stream.ksrate_capability, ks/PKSRATE_CAPABILITY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
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
-	ks.h
apiname:
-	KSRATE_CAPABILITY
product: Windows
targetos: Windows
req.typenames: "*PKSRATE_CAPABILITY, KSRATE_CAPABILITY"
---

# KSRATE_CAPABILITY structure


## -description


The client uses the KSRATE_CAPABILITY structure in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565756">KSPROPERTY_STREAM_RATECAPABILITY</a> property request.


## -syntax


````
typedef struct {
  KSPROPERTY Property;
  KSRATE     Rate;
} KSRATE_CAPABILITY, *PKSRATE_CAPABILITY;
````


## -struct-fields




### -field Property

A structure of type <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> that specifies the property identifier.


### -field Rate

A structure of type <a href="..\ks\ns-ks-ksrate.md">KSRATE</a> that specifies the requested rate.

