---
UID: NF:ndis.NdisFRestartComplete
title: NdisFRestartComplete function (ndis.h)
description: A filter driver must call the NdisFRestartComplete function to complete a restart operation if the driver returned NDIS_STATUS_PENDING from its FilterRestart function.
old-location: netvista\ndisfrestartcomplete.htm
tech.root: netvista
ms.assetid: 84685763-e7d8-4184-afa3-83efb4a0d3d7
ms.date: 05/02/2018
keywords: ["NdisFRestartComplete function"]
ms.keywords: NdisFRestartComplete, NdisFRestartComplete function [Network Drivers Starting with Windows Vista], filter_ndis_functions_ref_592af2b7-2172-4a8d-aa7b-315f7c321705.xml, ndis/NdisFRestartComplete, netvista.ndisfrestartcomplete
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisFRestartComplete
 - ndis/NdisFRestartComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisFRestartComplete
---

# NdisFRestartComplete function


## -description

A filter driver must call the 
  <b>NdisFRestartComplete</b> function to complete a restart operation if the driver returned
  NDIS_STATUS_PENDING from its 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_restart">FilterRestart</a> function.

## -parameters

### -param NdisFilterHandle 

[in]
The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a> function.

### -param Status 

[in]
The final status of the restart operation. The following status values are supported:
     





#### NDIS_STATUS_SUCCESS

The driver successfully restarted the flow of network data.



#### NDIS_STATUS_RESOURCES

The restart failed because of insufficient resources.



#### NDIS_STATUS_FAILURE

The driver indicates NDIS_STATUS_FAILURE if none of the preceding values applies. The driver
       should call the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswriteeventlogentry">NdisWriteEventLogEntry</a> function
       together with parameters that specify the reason for the failure.

## -remarks

NDIS calls a filter driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_restart">FilterRestart</a> function to initiate a
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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_restart">FilterRestart</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswriteeventlogentry">NdisWriteEventLogEntry</a>

