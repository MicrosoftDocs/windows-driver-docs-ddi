---
UID: NF:ndis.NdisFNetPnPEvent
title: NdisFNetPnPEvent function
author: windows-driver-content
description: A filter driver can call the NdisFNetPnPEvent function to forward a network Plug and Play (PnP) or Power Management event to overlying drivers.
old-location: netvista\ndisfnetpnpevent.htm
old-project: netvista
ms.assetid: 383f9dcb-68ba-4323-b25f-668169043f35
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisFNetPnPEvent
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
req.alt-api: NdisFNetPnPEvent
req.alt-loc: ndis.lib,ndis.dll
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
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisFNetPnPEvent function



## -description
A filter driver can call the 
  <b>NdisFNetPnPEvent</b> function to forward a network Plug and Play (PnP) or Power Management event to
  overlying drivers.



## -syntax

````
NDIS_STATUS NdisFNetPnPEvent(
  _In_ NDIS_HANDLE                 FilterModuleContext,
  _In_ PNET_PNP_EVENT_NOTIFICATION NetPnPEvent
);
````


## -parameters

### -param FilterModuleContext [in]

A handle to the context area for the filter module. The filter driver created and initialized this
     context area in the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.


### -param NetPnPEvent [in]

A pointer to a 
     <a href="..\ndis\ns-ndis-_net_pnp_event_notification.md">
     NET_PNP_EVENT_NOTIFICATION</a> structure, which describes the network PnP event or Power Management
     event being forwarded by the filter driver.


## -returns
<b>NdisFNetPnPEvent</b> can return either of the following:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>The overlying driver succeeded in processing the PnP event.
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>The overlying driver failed the PnP event.

 


## -remarks
NDIS calls a filter driver's 
    <a href="..\ndis\nc-ndis-filter_net_pnp_event.md">FilterNetPnPEvent</a> function to notify
    the filter driver of network PnP and Power Management events.

Filter drivers can forward these notifications to overlying drivers. To forward a request, call the 
    <b>NdisFNetPnPEvent</b> function from 
    <i>FilterNetPnPEvent</i>.


## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_net_pnp_event.md">FilterNetPnPEvent</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_oid_request.md">FilterOidRequest</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_pnp_event_notification.md">NET_PNP_EVENT_NOTIFICATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFNetPnPEvent function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

