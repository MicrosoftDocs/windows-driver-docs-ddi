---
UID: NC:61883.PBUS_RESET_ROUTINE
title: PBUS_RESET_ROUTINE
author: windows-driver-content
description: This is a caller-supplied function to be called by the protocol driver when the 1394 bus is reset.
old-location: ieee\pbus_reset_routine.htm
old-project: IEEE
ms.assetid: 99555765-A58F-45A1-B146-3742C390E666
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 61883/BusResetRoutine, BusResetRoutine, BusResetRoutine callback function [Buses], IEEE.pbus_reset_routine, PBUS_RESET_ROUTINE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: 61883.h
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
-	UserDefined
api_location:
-	61883.h
api_name:
-	BusResetRoutine
product:
- Windows
targetos: Windows
req.typenames: TOPOLOGY_MAP, *PTOPOLOGY_MAP
---

# PBUS_RESET_ROUTINE callback


## -description


This is a caller-supplied function to be called by the protocol driver when the 1394 bus is reset.


## -parameters




### -param Context [in]

Pointer to the context supplied by the caller at the <b>Context</b> member of the input BUS_RESET_NOTIFY structure. 


### -param BusResetInfo [in]

The bus reset information. 


## -returns



This callback does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>
 

 

