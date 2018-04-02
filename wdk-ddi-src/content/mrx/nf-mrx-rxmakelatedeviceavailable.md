---
UID: NF:mrx.RxMakeLateDeviceAvailable
title: RxMakeLateDeviceAvailable function
author: windows-driver-content
description: RxMakeLateDeviceAvailable modifies the device object to make a &#0034;late device&#0034; available. A late device is one that is not created in the driver's load routine.
old-location: ifsk\rxmakelatedeviceavailable.htm
old-project: ifsk
ms.assetid: 0818907f-3346-42a2-b123-3298ea8f9a1d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RxMakeLateDeviceAvailable, RxMakeLateDeviceAvailable routine [Installable File System Drivers], ifsk.rxmakelatedeviceavailable, mrx/RxMakeLateDeviceAvailable, rxref_7586550f-6abe-4e18-8154-09936c3f0488.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: mrx.h
req.include-header: Mrx.h, Rxstruc.h
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	mrx.h
api_name:
-	RxMakeLateDeviceAvailable
product:
- Windows
targetos: Windows
req.typenames: SetDSMCounters_IN, *PSetDSMCounters_IN
---

# RxMakeLateDeviceAvailable function


## -description


<b>RxMakeLateDeviceAvailable</b> modifies the device object to make a "late device" available. A late device is one that is not created in the driver's load routine.


## -parameters




### -param RxDeviceObject [in]

A pointer to the where the created device object is to be stored.


## -returns



None




## -remarks



<b>RxMakeLateDeviceAvailable</b> clears the DO_DEVICE_INITIALIZING bit in the <b>Flags</b> member of the device object. 



