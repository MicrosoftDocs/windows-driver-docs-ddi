---
UID: NF:ndis.NdisMOidRequestComplete
title: NdisMOidRequestComplete function
author: windows-driver-content
description: Miniport drivers call the NdisMOidRequestComplete function to return the final status of an OID request for which the driver's MiniportOidRequest function returned NDIS_STATUS_PENDING.
old-location: netvista\ndismoidrequestcomplete.htm
old-project: netvista
ms.assetid: 30d060d0-05a3-42b5-b5ff-2f2b12873ca9
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisMOidRequestComplete, ndis/NdisMOidRequestComplete, netvista.ndismoidrequestcomplete, ndis_request_ref_b5524732-acaf-4d0d-a261-3f8a8b739ecc.xml, NdisMOidRequestComplete function [Network Drivers Starting with Windows Vista]
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
req.ddi-compliance: DoubleComplete, DoubleCompleteWorkItem, Irql_OID_Function, NdisMNetPnPEventInOIDRequest, NdisOidComplete, NdisOidDoubleComplete, NdisOidDoubleRequest, NdisTimedOidComplete, WlanAssociation, WlanDisassociation, WlanTimedConnectRequest, WlanTimedLinkQuality, WlanTimedScan
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
-	NdisMOidRequestComplete
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMOidRequestComplete function


## -description


Miniport drivers call the 
  <b>NdisMOidRequestComplete</b> function to return the final status of an OID request for which the driver's 
  <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function returned
  NDIS_STATUS_PENDING.


## -syntax


````
VOID NdisMOidRequestComplete(
  _In_ NDIS_HANDLE       MiniportAdapterHandle,
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


### -param OidRequest [in]

A pointer to a buffer that is formatted as an 
     <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure. The miniport
     driver obtained this pointer as an input parameter to its 
     <i>MiniportOidRequest</i> function.


### -param Status [in]

The final status of the request operation, either NDIS_STATUS_SUCCESS,
     NDIS_STATUS_REQUEST_ABORTED, or any driver-determined NDIS_STATUS_<i>XXX</i><u>except</u> NDIS_STATUS_PENDING. For more information about OID status values, see 
     <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a>.


## -returns


None



## -remarks


A miniport driver that returns NDIS_STATUS_PENDING from its 
    <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function must
    call 
    <b>NdisMOidRequestComplete</b> after the miniport driver has finished the request operation.

A call to 
    <b>NdisMOidRequestComplete</b> causes a call to the request complete function (see 
    <a href="https://msdn.microsoft.com/2c383523-7d9c-4f1b-8df1-5cb4cc3562d6">ProtocolRequestComplete</a>, 
    <a href="..\ndis\nc-ndis-protocol_oid_request_complete.md">ProtocolOidRequestComplete</a>,
    
    <a href="..\ndis\nc-ndis-filter_oid_request_complete.md">FilterOidRequestComplete</a>) of
    the overlying driver that called the 
    <a href="..\ndis\nf-ndis-ndisoidrequest.md">NdisOidRequest</a> function.



## -see-also

<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>

<a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a>

<a href="..\ndis\nc-ndis-filter_oid_request_complete.md">FilterOidRequestComplete</a>

<a href="..\ndis\nf-ndis-ndisoidrequest.md">NdisOidRequest</a>

<a href="..\ndis\nc-ndis-protocol_oid_request_complete.md">ProtocolOidRequestComplete</a>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="https://msdn.microsoft.com/2c383523-7d9c-4f1b-8df1-5cb4cc3562d6">ProtocolRequestComplete</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMOidRequestComplete function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

