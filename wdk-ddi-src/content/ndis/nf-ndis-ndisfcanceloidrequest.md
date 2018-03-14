---
UID: NF:ndis.NdisFCancelOidRequest
title: NdisFCancelOidRequest function
author: windows-driver-content
description: Filter drivers call the NdisFCancelOidRequest function to cancel a previous request to the underlying drivers.
old-location: netvista\ndisfcanceloidrequest.htm
old-project: netvista
ms.assetid: 67dc0769-0d65-4048-84aa-1100883bde46
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisFCancelOidRequest, NdisFCancelOidRequest function [Network Drivers Starting with Windows Vista], ndis/NdisFCancelOidRequest, ndis_request_ref_17e19328-030e-4649-94c9-f7b0347e7ab2.xml, netvista.ndisfcanceloidrequest
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisFCancelOidRequest
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisFCancelOidRequest function


## -description


Filter drivers call the 
  <b>NdisFCancelOidRequest</b> function to cancel a previous request to the underlying drivers.


## -syntax


````
VOID NdisFCancelOidRequest(
  _In_ NDIS_HANDLE NdisFilterHandle,
  _In_ PVOID       RequestId
);
````


## -parameters




### -param NdisFilterHandle [in]

The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.


### -param RequestId [in]

A cancellation identifier for the request. This identifier specifies the 
     <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structures that are being
     canceled.


## -returns



None




## -remarks



Filter drivers call 
    <b>NdisFCancelOidRequest</b> to cancel a previously issued request. The request can be originated by the
    filter driver or by overlying drivers. The pointer passed at 
    <i>OidRequest</i> must be the same pointer that was passed in the call to the 
    <a href="..\ndis\nf-ndis-ndisfoidrequest.md">NdisFOidRequest</a> function.

The filter driver can call 
    <b>NdisFCancelOidRequest</b> from the 
    <a href="..\ndis\nc-ndis-filter_cancel_oid_request.md">FilterCancelOidRequest</a> function
    to pass on the cancellation to underlying drivers.




## -see-also

<a href="..\ndis\nc-ndis-filter_cancel_oid_request.md">FilterCancelOidRequest</a>



<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>



<a href="..\ndis\nf-ndis-ndisfoidrequest.md">NdisFOidRequest</a>



<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>



 

 


