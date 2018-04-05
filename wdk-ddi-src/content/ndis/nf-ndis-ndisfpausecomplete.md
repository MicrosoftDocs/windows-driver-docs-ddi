---
UID: NF:ndis.NdisFPauseComplete
title: NdisFPauseComplete function
author: windows-driver-content
description: A filter driver must call the NdisFPauseComplete function to complete a pause operation if the driver returned NDIS_STATUS_PENDING from its FilterPause function.
old-location: netvista\ndisfpausecomplete.htm
old-project: netvista
ms.assetid: 7f5730d3-6e6c-490f-b2e5-e2d3615b4c3a
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisFPauseComplete, NdisFPauseComplete function [Network Drivers Starting with Windows Vista], filter_ndis_functions_ref_2f2cd8ef-a148-49d2-a00d-ec0acef7e310.xml, ndis/NdisFPauseComplete, netvista.ndisfpausecomplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Filter_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisFPauseComplete
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisFPauseComplete function


## -description


A filter driver must call the 
  <b>NdisFPauseComplete</b> function to complete a pause operation if the driver returned NDIS_STATUS_PENDING
  from its 
  <a href="https://msdn.microsoft.com/a239889e-ec39-48fc-9e82-c8bc3d7ca51a">FilterPause</a> function.


## -parameters




### -param NdisFilterHandle [in]

The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a> function.


## -returns



None




## -remarks



NDIS calls a filter driver's 
    <a href="https://msdn.microsoft.com/a239889e-ec39-48fc-9e82-c8bc3d7ca51a">FilterPause</a> function to initiate a pause
    request for a filter module. The filter module remains in the 
    <i>Pausing</i> state until the pause operation is complete.

After a pending pause operation is complete, the driver calls 
    <b>NdisFPauseComplete</b> to notify NDIS. After the driver calls 
    <b>NdisFPauseComplete</b>, the filter module is in the 
    <i>Paused</i> state.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a>



<a href="https://msdn.microsoft.com/a239889e-ec39-48fc-9e82-c8bc3d7ca51a">FilterPause</a>
 

 

