---
UID: NF:ndis.NdisMCoOidRequestComplete
title: NdisMCoOidRequestComplete function
author: windows-driver-content
description: The NdisMCoOidRequestComplete function returns the final status of an OID requestthat a miniport driver's MiniportCoOidRequest function returned NDIS_STATUS_PENDING for.
old-location: netvista\ndismcooidrequestcomplete.htm
old-project: netvista
ms.assetid: 18242351-3dec-40df-b112-2335253903d2
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndismcooidrequestcomplete, NdisMCoOidRequestComplete function [Network Drivers Starting with Windows Vista], NdisMCoOidRequestComplete, ndis/NdisMCoOidRequestComplete, condis_request_ref_516edd5f-ceae-4330-87b1-48a3a383e736.xml
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
req.ddi-compliance: Irql_MCO_Function
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
-	NdisMCoOidRequestComplete
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisMCoOidRequestComplete function


## -description


The 
  <b>NdisMCoOidRequestComplete</b> function returns the final status of an OID requestthat a miniport driver's
  
  <a href="..\ndis\nc-ndis-miniport_co_oid_request.md">MiniportCoOidRequest</a> function
  returned NDIS_STATUS_PENDING for.


## -syntax


````
VOID NdisMCoOidRequestComplete(
  _In_ NDIS_HANDLE       MiniportAdapterHandle,
  _In_ NDIS_HANDLE       NdisVcHandle,
  _In_ PNDIS_OID_REQUEST OidRequest,
  _In_ NDIS_STATUS       Status
);
````


## -parameters




### -param MiniportAdapterHandle [in]

A miniport adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of the 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">
     MiniportInitializeEx</a> function.


### -param NdisMiniportVcHandle

TBD


### -param Request

TBD


### -param Status [in]

The final status of the request operation, either NDIS_STATUS_SUCCESS,
     NDIS_STATUS_REQUEST_ABORTED, or any driver-determined NDIS_STATUS_<i>XXX</i> value 
     <u>except</u> NDIS_STATUS_PENDING.


#### - NdisVcHandle [in]

A handle that identifies the virtual connection (VC). The miniport driver obtained this handle as
     an input parameter to its 
     <a href="..\ndis\nc-ndis-miniport_co_create_vc.md">MiniportCoCreateVc</a> function, either
     when a client set up an outgoing call or when the call manager created a VC for a client-registered
     service access point (SAP). The call manager created the VC to indicate an incoming-call notification.
     If the request is 
     <u>not</u> VC-specific, this parameter is <b>NULL</b>.


#### - OidRequest [in]

A pointer to a buffer that is formatted as an 
     <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure. The miniport
     driver obtained this pointer as an input parameter to its 
     <a href="..\ndis\nc-ndis-miniport_co_oid_request.md">
     MiniportCoOidRequest</a> function.


## -returns



None




## -remarks



A CoNDIS miniport driver that returns NDIS_STATUS_PENDING from its 
    <a href="..\ndis\nc-ndis-miniport_co_oid_request.md">MiniportCoOidRequest</a> function must
    call 
    <b>NdisMCoOidRequestComplete</b> after the miniport driver has finished the request operation.

A call to 
    <b>NdisMCoOidRequestComplete</b> causes a call to the 
    <a href="..\ndis\nc-ndis-protocol_co_oid_request_complete.md">
    ProtocolCoOidRequestComplete</a> function of the overlying driver that called the 
    <a href="..\ndis\nf-ndis-ndiscooidrequest.md">NdisCoOidRequest</a> function.




## -see-also

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nc-ndis-protocol_co_oid_request_complete.md">
   ProtocolCoOidRequestComplete</a>



<a href="..\ndis\nf-ndis-ndiscooidrequest.md">NdisCoOidRequest</a>



<a href="..\ndis\nc-ndis-miniport_co_oid_request.md">MiniportCoOidRequest</a>



<a href="..\ndis\nc-ndis-miniport_co_create_vc.md">MiniportCoCreateVc</a>



<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMCoOidRequestComplete function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

