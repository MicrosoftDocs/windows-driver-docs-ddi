---
UID: NF:ks.KsGetDefaultClockTime
title: KsGetDefaultClockTime function
author: windows-driver-content
description: The KsGetDefaultClockTime function gets the current time of the clock.The function can be called at DISPATCH_LEVEL.
old-location: stream\ksgetdefaultclocktime.htm
old-project: stream
ms.assetid: 9689b9f8-e5ae-4689-90b1-6d029408f876
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsGetDefaultClockTime, KsGetDefaultClockTime function [Streaming Media Devices], ks/KsGetDefaultClockTime, ksfunc_16bfafe4-e317-48e9-841f-f642eb1fb8d3.xml, stream.ksgetdefaultclocktime
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsGetDefaultClockTime
product: Windows
targetos: Windows
req.typenames: 
---

# KsGetDefaultClockTime function


## -description


The <b>KsGetDefaultClockTime</b> function gets the current time of the clock.

The function can be called at DISPATCH_LEVEL.


## -syntax


````
LONGLONG KsGetDefaultClockTime(
  _In_ PKSDEFAULTCLOCK DefaultClock
);
````


## -parameters




### -param DefaultClock [in]

Specifies an initialize default clock structure that is shared among any instance of the default clock for the parent. 


## -returns



The <b>KsGetDefaultClockTime</b> function returns the current clock time.




## -see-also

<a href="..\ks\nf-ks-kssetdefaultclocktime.md">KsSetDefaultClockTime</a>



 

 


