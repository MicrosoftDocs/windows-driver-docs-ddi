---
UID: NF:ndis.NdisMPauseComplete
title: NdisMPauseComplete function
author: windows-driver-content
description: A miniport driver must call the NdisMPauseComplete function to complete a pause operation if the driver returned NDIS_STATUS_PENDING from its MiniportPause function.
old-location: netvista\ndismpausecomplete.htm
old-project: netvista
ms.assetid: 08a9dccf-53bc-4b96-a794-14ead08a7b0b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisMPauseComplete, ndis/NdisMPauseComplete, netvista.ndismpausecomplete, miniport_ndis_functions_ref_1e76f7bc-a042-4a7a-8dc6-0f4cc6f7617f.xml, NdisMPauseComplete function [Network Drivers Starting with Windows Vista]
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
req.ddi-compliance: Irql_Miniport_Driver_Function
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
-	NdisMPauseComplete
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisMPauseComplete function


## -description


A miniport driver must call the 
  <b>NdisMPauseComplete</b> function to complete a pause operation if the driver returned NDIS_STATUS_PENDING
  from its 
  <a href="..\ndis\nc-ndis-miniport_pause.md">MiniportPause</a> function.


## -syntax


````
VOID NdisMPauseComplete(
  _In_ NDIS_HANDLE MiniportAdapterHandle
);
````


## -parameters




### -param MiniportAdapterHandle [in]

The miniport adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>.


## -returns



None




## -remarks



NDIS calls a miniport driver's 
    <a href="..\ndis\nc-ndis-miniport_pause.md">MiniportPause</a> function to initiate a
    pause request for a miniport adapter. The miniport adapter remains in the 
    <i>Pausing</i> state until the pause operation is complete.

After a miniport driver completes all outstanding send requests and NDIS returns all the network data
    structures in outstanding receive indications to the driver, the driver calls 
    <b>NdisMPauseComplete</b> to complete the pending pause request. After the driver calls 
    <b>NdisMPauseComplete</b>, the miniport adapter is in the 
    <i>Paused</i> state.

NDIS calls the 
    <a href="..\ndis\nc-ndis-miniport_restart.md">MiniportRestart</a> function to initiate a
    restart request for a miniport adapter that is paused.




## -see-also

<a href="..\ndis\nc-ndis-miniport_restart.md">MiniportRestart</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nc-ndis-miniport_pause.md">MiniportPause</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMPauseComplete function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

