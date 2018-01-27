---
UID: NC:strmini.PHW_INTERRUPT
title: PHW_INTERRUPT
author: windows-driver-content
description: StrMiniInterrupt is the minidriver's interrupt service routine.
old-location: stream\strminiinterrupt.htm
old-project: stream
ms.assetid: a98986c6-f4ac-4e2e-9ba0-49fec6684158
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.strminiinterrupt, StrMiniInterrupt, StrMiniInterrupt routine [Streaming Media Devices], StrMiniInterrupt, PHW_INTERRUPT, PHW_INTERRUPT, strmini/StrMiniInterrupt, strmini-routines_10ec4194-fc96-49da-a7d7-e7e90ead67e3.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: strmini.h
req.include-header: Strmini.h
req.target-type: Desktop
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
-	UserDefined
apilocation: 
-	strmini.h
apiname: 
-	StrMiniInterrupt
product: Windows
targetos: Windows
req.typenames: ZONE_DESCRIPTIOR, *PZONE_DESCRIPTIOR
req.product: Windows 10 or later.
---

# PHW_INTERRUPT callback


## -description


<i>StrMiniInterrupt</i> is the minidriver's interrupt service routine.


## -prototype


````
PHW_INTERRUPT StrMiniInterrupt;

VOID StrMiniInterrupt(
  _In_ PVOID DeviceExtension
)
{ ... }
````


## -parameters




### -param DeviceExtension [in]

Pointer to the minidriver's device extension.


## -returns


<i>StrMiniInterrupt</i> returns <b>TRUE</b> if the device generated the interrupt, and <b>FALSE</b> otherwise.



## -remarks


The class driver calls <i>StrMiniInterrupt</i> each time it receives an interrupt on behalf of the minidriver.

An interrupt may be shared among several different devices. The minidriver's <i>StrMiniInterrupt</i> routine must determine if its underlying hardware actually generated the interrupt. If the device did not generate the interrupt, <i>StrMiniInterrupt</i> should return <b>FALSE</b> as soon as possible -- for shared interrupts, the operating system calls the interrupt service routines registered for that interrupt until one of the routines returns <b>TRUE</b>, so the ISR may keep the actual device that generated the interrupt waiting if it takes too long to complete.


