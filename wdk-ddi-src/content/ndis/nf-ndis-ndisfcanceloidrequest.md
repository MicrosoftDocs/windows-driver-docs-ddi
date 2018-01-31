---
UID: NF:ndis.NdisFCancelOidRequest
title: NdisFCancelOidRequest function
author: windows-driver-content
description: Filter drivers call the NdisFCancelOidRequest function to cancel a previous request to the underlying drivers.
old-location: netvista\ndisfcanceloidrequest.htm
old-project: netvista
ms.assetid: 67dc0769-0d65-4048-84aa-1100883bde46
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis/NdisFCancelOidRequest, ndis_request_ref_17e19328-030e-4649-94c9-f7b0347e7ab2.xml, NdisFCancelOidRequest, NdisFCancelOidRequest function [Network Drivers Starting with Windows Vista], netvista.ndisfcanceloidrequest
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




#### - NdisFilterHandle [in]

The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.


#### - RequestId [in]

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

<a href="..\ndis\nf-ndis-ndisfoidrequest.md">NdisFOidRequest</a>

<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>

<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>

<a href="..\ndis\nc-ndis-filter_cancel_oid_request.md">FilterCancelOidRequest</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFCancelOidRequest function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

