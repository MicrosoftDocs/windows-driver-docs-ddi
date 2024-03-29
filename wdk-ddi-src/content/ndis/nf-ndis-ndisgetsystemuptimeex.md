---
UID: NF:ndis.NdisGetSystemUpTimeEx
title: NdisGetSystemUpTimeEx function (ndis.h)
description: The NdisGetSystemUpTimeEx function returns the number of milliseconds that have elapsed since the computer was restarted.
old-location: netvista\ndisgetsystemuptimeex.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisGetSystemUpTimeEx function"]
ms.keywords: NdisGetSystemUpTimeEx, NdisGetSystemUpTimeEx function [Network Drivers Starting with Windows Vista], ndis/NdisGetSystemUpTimeEx, ndis_timer_ref_d487ece6-5ab0-4386-bd6e-1eaecbabf903.xml, netvista.ndisgetsystemuptimeex
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisGetSystemUpTimeEx
 - ndis/NdisGetSystemUpTimeEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisGetSystemUpTimeEx
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

## -remarks

NDIS drivers should call the 
    <b>NdisGetSystemUpTimeEx</b> function instead of the 
    <a href="/previous-versions/windows/hardware/network/ff552110(v=vs.85)">NdisGetSystemUpTime</a> function.

## -see-also

<a href="/previous-versions/windows/hardware/network/ff552110(v=vs.85)">NdisGetSystemUpTime</a>
