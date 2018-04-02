---
UID: NF:ndis.NdisGetSystemUpTimeEx
title: NdisGetSystemUpTimeEx function
author: windows-driver-content
description: The NdisGetSystemUpTimeEx function returns the number of milliseconds that have elapsed since the computer was restarted.
old-location: netvista\ndisgetsystemuptimeex.htm
old-project: netvista
ms.assetid: a52087b5-81de-4945-9d1e-bea67915ced4
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisGetSystemUpTimeEx, NdisGetSystemUpTimeEx function [Network Drivers Starting with Windows Vista], ndis/NdisGetSystemUpTimeEx, ndis_timer_ref_d487ece6-5ab0-4386-bd6e-1eaecbabf903.xml, netvista.ndisgetsystemuptimeex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.lib: Ndis.lib
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisGetSystemUpTimeEx
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisGetSystemUpTimeEx function


## -description


The 
  <b>NdisGetSystemUpTimeEx</b> function returns the number of milliseconds that have elapsed since the
  computer was restarted.


## -parameters




### -param pSystemUpTime [out]

A pointer to a caller-supplied LARGE_INTEGER variable in which this function returns the time, in
     milliseconds, since the computer was last restarted.


## -returns



None




## -remarks



NDIS drivers should call the 
    <b>NdisGetSystemUpTimeEx</b> function instead of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff552110">NdisGetSystemUpTime</a> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552110">NdisGetSystemUpTime</a>
 

 

