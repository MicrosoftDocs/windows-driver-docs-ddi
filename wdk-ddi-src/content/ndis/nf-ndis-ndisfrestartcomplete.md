---
UID: NF:ndis.NdisFRestartComplete
title: NdisFRestartComplete function
author: windows-driver-content
description: A filter driver must call the NdisFRestartComplete function to complete a restart operation if the driver returned NDIS_STATUS_PENDING from its FilterRestart function.
old-location: netvista\ndisfrestartcomplete.htm
old-project: netvista
ms.assetid: 84685763-e7d8-4184-afa3-83efb4a0d3d7
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndisfrestartcomplete, filter_ndis_functions_ref_592af2b7-2172-4a8d-aa7b-315f7c321705.xml, ndis/NdisFRestartComplete, NdisFRestartComplete, NdisFRestartComplete function [Network Drivers Starting with Windows Vista]
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisFRestartComplete
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisFRestartComplete function


## -description


A filter driver must call the 
  <b>NdisFRestartComplete</b> function to complete a restart operation if the driver returned
  NDIS_STATUS_PENDING from its 
  <a href="..\ndis\nc-ndis-filter_restart.md">FilterRestart</a> function.


## -syntax


````
VOID NdisFRestartComplete(
  _In_ NDIS_HANDLE NdisFilterHandle,
  _In_ NDIS_STATUS Status
);
````


## -parameters




### -param NdisFilterHandle [in]

The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.


### -param Status [in]

The final status of the restart operation. The following status values are supported:
     





#### NDIS_STATUS_SUCCESS

The driver successfully restarted the flow of network data.



#### NDIS_STATUS_RESOURCES

The restart failed because of insufficient resources.



#### NDIS_STATUS_FAILURE

The driver indicates NDIS_STATUS_FAILURE if none of the preceding values applies. The driver
       should call the 
       <a href="..\ndis\nf-ndis-ndiswriteeventlogentry.md">NdisWriteEventLogEntry</a> function
       together with parameters that specify the reason for the failure.


## -returns



None




## -remarks



NDIS calls a filter driver's 
    <a href="..\ndis\nc-ndis-filter_restart.md">FilterRestart</a> function to initiate a
    restart request for filter module. The filter module remains in the 
    <i>Restarting</i> state until the restart operation is complete.

A pending restart operation is complete after the driver calls the 
    <b>NdisFRestartComplete</b> function. The filter module is in the 
    <i>Running</i> state after the restart operation is complete.

A filter driver can resume indicating received network data immediately after NDIS calls 
    <i>FilterRestart</i> and before the driver calls 
    <b>NdisFRestartComplete</b>. The driver should be ready to accept send requests after it completes the
    restart operation.




## -see-also

<a href="..\ndis\nf-ndis-ndiswriteeventlogentry.md">NdisWriteEventLogEntry</a>



<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>



<a href="..\ndis\nc-ndis-filter_restart.md">FilterRestart</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFRestartComplete function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

