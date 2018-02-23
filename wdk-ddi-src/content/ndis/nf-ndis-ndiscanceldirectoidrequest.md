---
UID: NF:ndis.NdisCancelDirectOidRequest
title: NdisCancelDirectOidRequest function
author: windows-driver-content
description: Protocol drivers call the NdisCancelDirectOidRequest function to cancel a previous direct OID request to the underlying drivers.
old-location: netvista\ndiscanceldirectoidrequest.htm
old-project: netvista
ms.assetid: bfccd901-9ce7-4873-ba9a-0e4718fd7d19
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ndis/NdisCancelDirectOidRequest, NdisCancelDirectOidRequest, netvista.ndiscanceldirectoidrequest, NdisCancelDirectOidRequest function [Network Drivers Starting with Windows Vista], ndis_request_direct_ref_71cb0f66-b7f7-49b5-b006-ca50eff45bcb.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
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
-	NdisCancelDirectOidRequest
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisCancelDirectOidRequest function


## -description


Protocol drivers call the 
  <b>NdisCancelDirectOidRequest</b> function to cancel a previous direct OID request to the underlying
  drivers.


## -syntax


````
VOID NdisCancelDirectOidRequest(
  _In_ NDIS_HANDLE NdisBindingHandle,
  _In_ PVOID       RequestId
);
````


## -parameters




### -param NdisBindingHandle [in]

The handle that the 
     <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function returned
     that identifies the target miniport adapter on the binding.


### -param RequestId [in]

A cancellation identifier for the request. This identifier specifies the 
     <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structures that are being
     canceled.


## -returns



None




## -remarks



Protocol drivers call the 
    <b>NdisCancelDirectOidRequest</b> function to cancel a previously issued direct OID request. The request
    ID that is passed at the 
    <i>RequestId</i> parameter must match the request ID in the 
    <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure that was passed
    in the call to the 
    <a href="..\ndis\nf-ndis-ndisdirectoidrequest.md">NdisDirectOidRequest</a> function.




## -see-also

<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>



<a href="..\ndis\nf-ndis-ndisdirectoidrequest.md">NdisDirectOidRequest</a>



<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCancelDirectOidRequest function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

