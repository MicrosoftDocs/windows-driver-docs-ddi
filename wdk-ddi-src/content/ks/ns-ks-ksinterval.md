---
UID: NS:ks.KSINTERVAL
title: KSINTERVAL
author: windows-driver-content
description: The KSINTERVAL structure specifies a base time and time interval for recurring events.
old-location: stream\ksinterval.htm
old-project: stream
ms.assetid: 9e363bd1-3bfd-48cc-adc1-a14d23868a57
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSINTERVAL, KSINTERVAL, KSINTERVAL structure [Streaming Media Devices], PKSINTERVAL, PKSINTERVAL structure pointer [Streaming Media Devices], ks-struct_56fded71-9af4-46a7-b872-1660582179ad.xml, ks/KSINTERVAL, ks/PKSINTERVAL, stream.ksinterval"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KSINTERVAL
product: Windows
targetos: Windows
req.typenames: KSINTERVAL, *PKSINTERVAL
---

# KSINTERVAL structure


## -description


The KSINTERVAL structure specifies a base time and time interval for recurring events.


## -struct-fields




### -field TimeBase

Specifies a 64-bit time base.


### -field Interval

Specifies a recurrence interval, also 64-bit.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561805">KSEVENT_CLOCK_INTERVAL_MARK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561811">KSEVENT_CLOCK_POSITION_MARK</a>
 

 

