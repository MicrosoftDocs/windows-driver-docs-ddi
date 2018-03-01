---
UID: NC:ndis.FILTER_NET_PNP_EVENT
title: FILTER_NET_PNP_EVENT
author: windows-driver-content
description: NDIS calls a filter driver's FilterNetPnPEvent function to notify the driver of network Plug and Play (PnP) and Power Management events.Note  You must declare the function by using the FILTER_NET_PNP_EVENT type.
old-location: netvista\filternetpnpevent.htm
old-project: netvista
ms.assetid: 5c52b2d2-3fba-4d28-8172-7b6854386061
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: FILTER_NET_PNP_EVENT, FilterNetPnPEvent, FilterNetPnPEvent callback function [Network Drivers Starting with Windows Vista], filter_functions_ref_4d98cb8b-3f25-4e2c-abca-ac9c714f4a1a.xml, ndis/FilterNetPnPEvent, netvista.filternetpnpevent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	FilterNetPnPEvent
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# FILTER_NET_PNP_EVENT callback


## -description


NDIS calls a filter driver's 
  <i>FilterNetPnPEvent</i> function to notify the driver of network Plug and Play (PnP)
  and Power Management events.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>FILTER_NET_PNP_EVENT</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
FILTER_NET_PNP_EVENT FilterNetPnPEvent;

NDIS_STATUS FilterNetPnPEvent(
  _In_ NDIS_HANDLE                 FilterModuleContext,
  _In_ PNET_PNP_EVENT_NOTIFICATION NetPnPEvent
)
{ ... }
````


## -parameters




### -param FilterModuleContext [in]

A handle to the context area for the filter module. The filter driver created and initialized this
     context area in the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.


### -param NetPnPEventNotification








#### - NetPnPEvent [in]

A pointer to a 
     <a href="..\ndis\ns-ndis-_net_pnp_event_notification.md">
     NET_PNP_EVENT_NOTIFICATION</a> structure, which describes the PnP event or Power Management event
     being indicated to the filter driver.


## -returns



<i>FilterNetPnPEvent</i> can return either of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The driver successfully processed the PnP event.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
The driver failed the PnP event.

</td>
</tr>
</table>
 

The return value is significant only when the propagated event is a 
     <b>NetEventQueryPower</b> or a 
     <b>NetEventQueryRemove</b> event. For all other propagated events, the return
     value is always NDIS_STATUS_SUCCESS.




## -remarks



<i>FilterNetPnPEvent</i> is an optional function. If a filter driver does not handle
    network PnP events, it can set the entry point for this function to <b>NULL</b> when it calls the 
    <a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">
    NdisFRegisterFilterDriver</a> function.

<i>FilterNetPnPEvent</i> is similar to a protocol driver's 
    <a href="..\ndis\nc-ndis-protocol_net_pnp_event.md">ProtocolNetPnPEvent</a> function. A
    filter driver can forward these notifications to overlying drivers or it can handle them itself and not
    forward them. To forward a notification, call the 
    <a href="..\ndis\nf-ndis-ndisfnetpnpevent.md">NdisFNetPnPEvent</a> function. Do not confuse
    this function with the 
    <a href="..\ndis\nc-ndis-filter_device_pnp_event_notify.md">
    FilterDevicePnPEventNotify</a> function, which filters notifications that are directed down the stack
    to underlying drivers.

NDIS calls 
    <i>FilterNetPnPEvent</i> to notify a filter driver of a PnP or Power Management event
    that was issued for an underlying NIC. NDIS calls the 
    <i>FilterNetPnPEvent</i> function of each filter driver overlying a NIC, and then
    calls the 
    <i>ProtocolNetPnPEvent</i> function of each overlying protocol driver.

When a filter module is inserted into or deleted from a driver stack, the characteristics of the stack
    might change. NDIS sends a PnP event to all affected protocol bindings and filter modules to notify them
    about this change. Filter drivers should handle such changes appropriately.

NDIS calls 
    <i>FilterNetPnPEvent</i> at IRQL = PASSIVE_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>FilterNetPnPEvent</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>FilterNetPnPEvent</i> function that is named "MyNetPnPEvent", use the <b>FILTER_NET_PNP_EVENT</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>FILTER_NET_PNP_EVENT MyNetPnPEvent;</pre>
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
NDIS_STATUS
 MyNetPnPEvent(
    NDIS_HANDLE  FilterModuleContext,
    PNET_PNP_EVENT_NOTIFICATION  NetPnPEvent
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>FILTER_NET_PNP_EVENT</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>FILTER_NET_PNP_EVENT</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also

<a href="..\ndis\ns-ndis-_net_pnp_event_notification.md">NET_PNP_EVENT_NOTIFICATION</a>



<a href="..\ndis\nf-ndis-ndisfnetpnpevent.md">NdisFNetPnPEvent</a>



<a href="..\ndis\nc-ndis-protocol_net_pnp_event.md">ProtocolNetPnPEvent</a>



<a href="..\ndis\nc-ndis-filter_device_pnp_event_notify.md">FilterDevicePnPEventNotify</a>



<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>



<a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">NdisFRegisterFilterDriver</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FILTER_NET_PNP_EVENT callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

