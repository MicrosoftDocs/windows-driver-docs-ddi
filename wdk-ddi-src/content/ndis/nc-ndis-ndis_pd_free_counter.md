---
UID: NC:ndis.NDIS_PD_FREE_COUNTER
title: NDIS_PD_FREE_COUNTER
author: windows-driver-content
description: The PacketDirect (PD) platform calls a PD-capable miniport driver's NdisPDFreeCounter function to free a counter object.
old-location: netvista\ndispdfreecounter.htm
old-project: netvista
ms.assetid: 60C47437-A999-4F82-B144-6F77410E5C07
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndispdfreecounter, NdisPDFreeCounter callback function [Network Drivers Starting with Windows Vista], NdisPDFreeCounter, NDIS_PD_FREE_COUNTER, NDIS_PD_FREE_COUNTER, ndis/NdisPDFreeCounter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	Ndis.h
apiname: 
-	NdisPDFreeCounter
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# NDIS_PD_FREE_COUNTER callback


## -description


The PacketDirect (PD) platform calls a PD-capable miniport driver's 
   <i>NdisPDFreeCounter</i> function to free a counter object.<div class="alert"><b>Note</b>  You must declare the function by using the <b>NDIS_PD_FREE_COUNTER</b> type. For more
   information, see the following Examples section.</div>
<div> </div>



## -prototype


````
NDIS_PD_FREE_COUNTER NdisPDFreeCounter;

void NdisPDFreeCounter(
  _In_ __drv_freesMem (Mem) NDIS_PD_COUNTER_HANDLE CounterHandle
)
{ ... }
````


## -parameters




### -param CounterHandle [in]

A counter handle that the miniport driver allocated in its <a href="..\ndis\nc-ndis-ndis_pd_allocate_counter.md">NdisPDAllocateCounter</a> function.


## -returns


This callback function does not return a value.



## -see-also

<a href="..\ndis\nc-ndis-ndis_pd_allocate_counter.md">NdisPDAllocateCounter</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PD_FREE_COUNTER callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

