---
UID: NS:ks.__unnamed_struct_60
title: KSRESOLUTION (ks.h)
description: The KSRESOLUTION structure specifies granularity and error of a kernel streaming clock.
old-location: stream\ksresolution.htm
tech.root: stream
ms.assetid: fbd6222c-6d54-4e2a-aa5b-8051f0838886
ms.date: 04/23/2018
ms.keywords: "*PKSRESOLUTION, KSRESOLUTION, KSRESOLUTION structure [Streaming Media Devices], PKSRESOLUTION, PKSRESOLUTION structure pointer [Streaming Media Devices], ks-struct_eb48cf83-0b80-4955-89a4-0b363497bef5.xml, ks/KSRESOLUTION, ks/PKSRESOLUTION, stream.ksresolution"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KSRESOLUTION
product:
- Windows
targetos: Windows
req.typenames: KSRESOLUTION, *PKSRESOLUTION
---

# KSRESOLUTION structure


## -description


The KSRESOLUTION structure specifies granularity and error of a kernel streaming clock.


## -struct-fields




### -field Granularity

Specifies the increment granularity of the clock in 100-nanosecond units, where 1 is the best.


### -field Error

Specifies the +/- notification error of the clock in 100-nanosecond units, where 0 is the best, meaning the event notification granularity is as good as the increment granularity.


## -remarks



Vendors can supply a structure of type KSRESOLUTION in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565092">KSPROPERTY_CLOCK_RESOLUTION</a> property request.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565092">KSPROPERTY_CLOCK_RESOLUTION</a>
 

 

