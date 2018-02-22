---
UID: NF:ndis.NdisFreeTimerObject
title: NdisFreeTimerObject function
author: windows-driver-content
description: The NdisFreeTimerObject function frees a timer object that was allocated with the NdisAllocateTimerObject function.
old-location: netvista\ndisfreetimerobject.htm
old-project: netvista
ms.assetid: b3edeebb-7a8f-4cd2-bd52-1b8ce044caa2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisFreeTimerObject function [Network Drivers Starting with Windows Vista], ndis_timer_ref_0f4b2edb-47fb-481c-a1e9-6940d15cb354.xml, ndis/NdisFreeTimerObject, NdisFreeTimerObject, netvista.ndisfreetimerobject
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
req.ddi-compliance: Irql_Timer_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisFreeTimerObject
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisFreeTimerObject function


## -description


The 
  <b>NdisFreeTimerObject</b> function frees a timer object that was allocated with the 
  <a href="..\ndis\nf-ndis-ndisallocatetimerobject.md">
  NdisAllocateTimerObject</a> function.


## -syntax


````
VOID NdisFreeTimerObject(
  _In_ NDIS_HANDLE TimerObject
);
````


## -parameters




### -param TimerObject [in]

A handle to a timer object that NDIS provides when a driver calls the 
     <a href="..\ndis\nf-ndis-ndisallocatetimerobject.md">
     NdisAllocateTimerObject</a> function.


## -returns



None




## -remarks



To use timer services, an NDIS driver first calls the 
    <a href="..\ndis\nf-ndis-ndisallocatetimerobject.md">NdisAllocateTimerObject</a> function
    to initialize a timer object. Typically, 
    <b>NdisAllocateTimerObject</b> is called when a driver initializes. The driver must call 
    <b>NdisFreeTimerObject</b> to free the timer object when the timer is no longer required.

To cancel a timer, call the 
    <a href="..\ndis\nf-ndis-ndiscanceltimerobject.md">NdisCancelTimerObject</a> function. 
    <b>NdisCancelTimerObject</b> dequeues the timer object if it is currently queued.




## -see-also

<a href="..\ndis\nf-ndis-ndiscanceltimerobject.md">NdisCancelTimerObject</a>



<a href="..\ndis\ns-ndis-_ndis_timer_characteristics.md">NDIS_TIMER_CHARACTERISTICS</a>



<a href="..\ndis\nf-ndis-ndisallocatetimerobject.md">NdisAllocateTimerObject</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFreeTimerObject function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

