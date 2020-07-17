---
UID: NC:ndis.FILTER_DEVICE_PNP_EVENT_NOTIFY
title: FILTER_DEVICE_PNP_EVENT_NOTIFY (ndis.h)
description: NDIS calls a filter driver's FilterDevicePnPEventNotify function to notify the driver of device Plug and Play (PnP) and Power Management events.Note  You must declare the function by using the FILTER_DEVICE_PNP_EVENT_NOTIFY type.
old-location: netvista\filterdevicepnpeventnotify.htm
tech.root: netvista
ms.assetid: dea4ab30-ba1d-4c9c-9f00-e48cc3cc0b46
ms.date: 05/02/2018
keywords: ["FILTER_DEVICE_PNP_EVENT_NOTIFY callback function"]
ms.keywords: FILTER_DEVICE_PNP_EVENT_NOTIFY, FILTER_DEVICE_PNP_EVENT_NOTIFY callback, FilterDevicePnPEventNotify, FilterDevicePnPEventNotify callback function [Network Drivers Starting with Windows Vista], filter_functions_ref_3e688903-ea36-44b3-bd06-533f7e573478.xml, ndis/FilterDevicePnPEventNotify, netvista.filterdevicepnpeventnotify
f1_keywords:
 - "ndis/FilterDevicePnPEventNotify"
 - "FilterDevicePnPEventNotify"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndis.h
api_name:
- FilterDevicePnPEventNotify
product:
- Windows
targetos: Windows
req.typenames: 
---

# FILTER_DEVICE_PNP_EVENT_NOTIFY callback function


## -description


NDIS calls a filter driver's 
  <i>FilterDevicePnPEventNotify</i> function to notify the driver of device Plug and Play (PnP) and Power
  Management events.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>FILTER_DEVICE_PNP_EVENT_NOTIFY</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param FilterModuleContext [in]

A handle to the context area for the filter module. The filter driver created and initialized this
     context area in the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a> function.


### -param NetDevicePnPEvent [in]

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_device_pnp_event">NET_DEVICE_PNP_EVENT</a> structure that
     describes a device Plug and Play event.


## -remarks



<i>FilterDevicePnPEventNotify</i> is an optional function. If a filter driver does not use device PnP
    requests, it can set the entry point for this function to <b>NULL</b> when it calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">
    NdisFRegisterFilterDriver</a> function.

<i>FilterDevicePnPEventNotify</i> is similar to a miniport driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_device_pnp_event_notify">
    MiniportDevicePnPEventNotify</a> function. Filter drivers can forward these notifications to underlying
    drivers. To forward a request, call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfdevicepnpeventnotify">
    NdisFDevicePnPEventNotify</a> function.

NDIS calls 
    <i>FilterDevicePnPEventNotify</i> at IRQL = PASSIVE_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>FilterDevicePnPEventNotify</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>FilterDevicePnPEventNotify</i> function that is named "MyDevicePnPEventNotify", use the <b>FILTER_DEVICE_PNP_EVENT_NOTIFY</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>FILTER_DEVICE_PNP_EVENT_NOTIFY MyDevicePnPEventNotify;</pre>
</td>
</tr>
</table></span></div>
Then, implement your function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyDevicePnPEventNotify(
    NDIS_HANDLE  FilterModuleContext,
    PNET_DEVICE_PNP_EVENT  NetDevicePnPEvent
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>FILTER_DEVICE_PNP_EVENT_NOTIFY</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>FILTER_DEVICE_PNP_EVENT_NOTIFY</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_device_pnp_event_notify">
   MiniportDevicePnPEventNotify</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_device_pnp_event">NET_DEVICE_PNP_EVENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfdevicepnpeventnotify">NdisFDevicePnPEventNotify</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">NdisFRegisterFilterDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswriteeventlogentry">NdisWriteEventLogEntry</a>
 

 

