---
UID: NF:ndis.NdisFPauseComplete
title: NdisFPauseComplete function
author: windows-driver-content
description: A filter driver must call the NdisFPauseComplete function to complete a pause operation if the driver returned NDIS_STATUS_PENDING from its FilterPause function.
old-location: netvista\ndisfpausecomplete.htm
old-project: netvista
ms.assetid: 7f5730d3-6e6c-490f-b2e5-e2d3615b4c3a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: filter_ndis_functions_ref_2f2cd8ef-a148-49d2-a00d-ec0acef7e310.xml, NdisFPauseComplete function [Network Drivers Starting with Windows Vista], NdisFPauseComplete, netvista.ndisfpausecomplete, ndis/NdisFPauseComplete
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisFPauseComplete
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisFPauseComplete function


## -description


A filter driver must call the 
  <b>NdisFPauseComplete</b> function to complete a pause operation if the driver returned NDIS_STATUS_PENDING
  from its 
  <a href="..\ndis\nc-ndis-filter_pause.md">FilterPause</a> function.


## -syntax


````
VOID NdisFPauseComplete(
  _In_ NDIS_HANDLE NdisFilterHandle
);
````


## -parameters




### -param NdisFilterHandle [in]

The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.


## -returns



None




## -remarks



NDIS calls a filter driver's 
    <a href="..\ndis\nc-ndis-filter_pause.md">FilterPause</a> function to initiate a pause
    request for a filter module. The filter module remains in the 
    <i>Pausing</i> state until the pause operation is complete.

After a pending pause operation is complete, the driver calls 
    <b>NdisFPauseComplete</b> to notify NDIS. After the driver calls 
    <b>NdisFPauseComplete</b>, the filter module is in the 
    <i>Paused</i> state.




## -see-also

<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>



<a href="..\ndis\nc-ndis-filter_pause.md">FilterPause</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFPauseComplete function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

