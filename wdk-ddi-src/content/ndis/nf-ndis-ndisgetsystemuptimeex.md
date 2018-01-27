---
UID: NF:ndis.NdisGetSystemUpTimeEx
title: NdisGetSystemUpTimeEx function
author: windows-driver-content
description: The NdisGetSystemUpTimeEx function returns the number of milliseconds that have elapsed since the computer was restarted.
old-location: netvista\ndisgetsystemuptimeex.htm
old-project: netvista
ms.assetid: a52087b5-81de-4945-9d1e-bea67915ced4
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis_timer_ref_d487ece6-5ab0-4386-bd6e-1eaecbabf903.xml, NdisGetSystemUpTimeEx, NdisGetSystemUpTimeEx function [Network Drivers Starting with Windows Vista], ndis/NdisGetSystemUpTimeEx, netvista.ndisgetsystemuptimeex
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	ndis.lib
-	ndis.dll
apiname: 
-	NdisGetSystemUpTimeEx
product: Windows
targetos: Windows
req.typenames: *PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE
---

# NdisGetSystemUpTimeEx function


## -description


The 
  <b>NdisGetSystemUpTimeEx</b> function returns the number of milliseconds that have elapsed since the
  computer was restarted.


## -syntax


````
VOID NdisGetSystemUpTimeEx(
  _Out_ PLARGE_INTEGER pSystemUpTime
);
````


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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisGetSystemUpTimeEx function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

