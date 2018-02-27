---
UID: NF:ndis.NdisCoOidRequestComplete
title: NdisCoOidRequestComplete function
author: windows-driver-content
description: The NdisCoOidRequestComplete function returns the final status of an OID request that a CoNDIS client's or stand-alone call manager's ProtocolCoOidRequest function previously returned NDIS_STATUS_PENDING for.
old-location: netvista\ndiscooidrequestcomplete.htm
old-project: netvista
ms.assetid: ba4a22a1-ad48-43f1-96f5-dee5d76e49cb
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisCoOidRequestComplete, NdisCoOidRequestComplete function [Network Drivers Starting with Windows Vista], condis_request_ref_29e0ae37-d6e6-4c75-b0fa-a6f84494f4a6.xml, ndis/NdisCoOidRequestComplete, netvista.ndiscooidrequestcomplete
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
req.ddi-compliance: Irql_Connection_Function
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
-	NdisCoOidRequestComplete
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisCoOidRequestComplete function


## -description


The 
  <b>NdisCoOidRequestComplete</b> function returns the final status of an OID request that a CoNDIS client's
  or stand-alone call manager's 
  <a href="..\ndis\nc-ndis-protocol_co_oid_request.md">ProtocolCoOidRequest</a> function
  previously returned NDIS_STATUS_PENDING for.


## -syntax


````
VOID NdisCoOidRequestComplete(
  _In_     NDIS_HANDLE       NdisAfHandle,
  _In_opt_ NDIS_HANDLE       NdisVcHandle,
  _In_opt_ NDIS_HANDLE       NdisPartyHandle,
  _In_     PNDIS_OID_REQUEST OidRequest,
  _In_     NDIS_STATUS       Status
);
````


## -parameters




### -param NdisAfHandle [in]

An address family (AF) handle that NDIS passed to the client or stand-alone call manager's 
     <a href="..\ndis\nc-ndis-protocol_co_oid_request.md">
     ProtocolCoOidRequest</a> function.


### -param NdisVcHandle [in, optional]

A virtual connection (VC) handle that NDIS passed to the client or stand-alone call manager's 
     <i>ProtocolCoOidRequest</i> function. A <b>NULL</b> value for this parameter indicates that the request is not
     VC-specific. This parameter is <b>NULL</b> if the caller of the 
     <a href="..\ndis\nf-ndis-ndiscooidrequest.md">NdisCoOidRequest</a> or 
     <a href="..\ndis\nf-ndis-ndismcmoidrequest.md">NdisMCmOidRequest</a> function specified a
     <b>NULL</b> VC handle.


### -param NdisPartyHandle [in, optional]

A party handle that NDIS passed to the client or stand-alone call manager's 
     <i>ProtocolCoOidRequest</i> function. A <b>NULL</b> value for this parameter indicates that the request is not
     party-specific. This parameter is <b>NULL</b> if the caller of the 
     <b>NdisCoOidRequest</b> or 
     <b>NdisMCmOidRequest</b> function specified a <b>NULL</b> party handle.


### -param OidRequest [in]

A pointer to a buffer that is formatted as an 
     <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure. The caller of
     the 
     <b>NdisCoOidRequest</b> or 
     <b>NdisMCmOidRequest</b> function supplied this buffer.


### -param Status [in]

The final status of the request operation, either NDIS_STATUS_SUCCESS, or any driver-determined
     NDIS_STATUS_<i>XXX</i> status value 
     except NDIS_STATUS_PENDING.


## -returns



None




## -remarks



A CoNDIS protocol driver that returns NDIS_STATUS_PENDING from its 
    <a href="..\ndis\nc-ndis-protocol_co_oid_request.md">ProtocolCoOidRequest</a> function must
    call 
    <b>NdisCoOidRequestComplete</b> after the protocol driver has finished the request operation.

After a driver calls 
    <b>NdisCoOidRequestComplete</b>, NDIS calls the 
    <a href="..\ndis\nc-ndis-protocol_co_oid_request_complete.md">
    ProtocolCoOidRequestComplete</a> function of the driver that originally called the 
    <a href="..\ndis\nf-ndis-ndiscooidrequest.md">NdisCoOidRequest</a> or 
    <a href="..\ndis\nf-ndis-ndismcmoidrequest.md">NdisMCmOidRequest</a> function.

Only clients and stand-alone call managers, which register themselves with NDIS as protocol drivers,
    can call 
    <b>NdisCoOidRequestComplete</b>. Miniport call managers (MCMs) call the 
    <a href="..\ndis\nf-ndis-ndismcmoidrequestcomplete.md">
    NdisMCmOidRequestComplete</a> function or 
    <a href="..\ndis\nf-ndis-ndismcooidrequestcomplete.md">
    NdisMCoOidRequestComplete</a> instead, depending on whether the MCM driver's 
    <a href="..\ndis\nc-ndis-protocol_co_oid_request.md">ProtocolCoOidRequest</a> or 
    <a href="..\ndis\nc-ndis-miniport_co_oid_request.md">MiniportCoOidRequest</a> function,
    respectively, handled the client's request.




## -see-also

<a href="..\ndis\nf-ndis-ndismcmoidrequestcomplete.md">NdisMCmOidRequestComplete</a>



<a href="..\ndis\nc-ndis-miniport_co_oid_request.md">MiniportCoOidRequest</a>



<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>



<a href="..\ndis\nf-ndis-ndiscooidrequest.md">NdisCoOidRequest</a>



<a href="..\ndis\nc-ndis-protocol_co_oid_request.md">ProtocolCoOidRequest</a>



<a href="..\ndis\nc-ndis-protocol_co_oid_request_complete.md">
   ProtocolCoOidRequestComplete</a>



<a href="..\ndis\nf-ndis-ndismcooidrequestcomplete.md">NdisMCoOidRequestComplete</a>



<a href="..\ndis\nf-ndis-ndismcmoidrequest.md">NdisMCmOidRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCoOidRequestComplete function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

