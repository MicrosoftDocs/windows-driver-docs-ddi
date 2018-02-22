---
UID: NF:ndis.NdisFOidRequest
title: NdisFOidRequest function
author: windows-driver-content
description: Filter drivers call the NdisFOidRequest function to forward an OID request to underlying drivers or to originate such a request.
old-location: netvista\ndisfoidrequest.htm
old-project: netvista
ms.assetid: 8434bf2c-9c9a-49a1-bf88-b67b1eec721c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisFOidRequest function [Network Drivers Starting with Windows Vista], NdisFOidRequest, netvista.ndisfoidrequest, ndis/NdisFOidRequest, ndis_request_ref_b5034fc8-9122-4c87-b690-a6989c1592c1.xml
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
req.ddi-compliance: Irql_OID_Function
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
-	NdisFOidRequest
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisFOidRequest function


## -description


Filter drivers call the 
  <b>NdisFOidRequest</b> function to forward an OID request to underlying drivers or to originate such a
  request.


## -syntax


````
NDIS_STATUS NdisFOidRequest(
  _In_ NDIS_HANDLE       NdisFilterHandle,
  _In_ PNDIS_OID_REQUEST OidRequest
);
````


## -parameters




### -param NdisFilterHandle [in]

An NDIS handle that identifies a filter module. NDIS passed the handle to the filter driver in a
     call to the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.


### -param OidRequest [in]

A pointer to an 
     <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure that specifies
     the operation requested with a given OID_<i>XXX</i> code. The structure can specify a query, set, or method request. For more information about
     OIDs, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566707">NDIS OIDs</a>.


## -returns



See the 
     <a href="..\ndis\nf-ndis-ndisoidrequest.md">NdisOidRequest</a> function.




## -remarks



Filter drivers can originate OID requests to underlying drivers by calling 
    <b>NdisFOidRequest</b>.

Filter drivers can also filter OID requests that are originated by overlying drivers. NDIS calls the 
    <a href="..\ndis\nc-ndis-filter_oid_request.md">FilterOidRequest</a> function to process
    each such request.

If 
    <b>NdisFOidRequest</b> returns <b>NDIS_STATUS_PENDING</b>, NDIS calls the 
    <a href="..\ndis\nc-ndis-filter_oid_request_complete.md">FilterOidRequestComplete</a> function after the underlying drivers complete the OID request.

If 
    <b>NdisFOidRequest</b> returns <b>NDIS_STATUS_SUCCESS</b>, it returns the results of a query request in the
    <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure at the 
    <i>OidRequest</i> parameter.

<b>NdisFOidRequest</b> can return <b>NDIS_STATUS_INVALID_PARAMETER</b> if the filter driver passes invalid values
    for the 
    <b>Type</b> and 
    <b>Size</b> fields in the 
    <b>Header</b> field of the 
    <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure.

A driver can call 
    <b>NdisFOidRequest</b> when it is in the 
    <i>Restarting</i>, 
    <i>Running</i>, 
    <i>Pausing</i>, or 
    <i>Paused</i> state.




## -see-also

<a href="..\ndis\nc-ndis-filter_oid_request_complete.md">FilterOidRequestComplete</a>



<a href="..\ndis\nc-ndis-filter_oid_request.md">FilterOidRequest</a>



<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>



<a href="..\ndis\nf-ndis-ndisoidrequest.md">NdisOidRequest</a>



<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFOidRequest function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

