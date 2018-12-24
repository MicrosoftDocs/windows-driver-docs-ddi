---
UID: NF:ndis.NdisCancelOidRequest
title: NdisCancelOidRequest function
description: Protocol drivers call the NdisCancelOidRequest function to cancel a previous request to the underlying drivers.
old-location: netvista\ndiscanceloidrequest.htm
tech.root: netvista
ms.assetid: 4cb12ac3-7cb6-4773-b680-d77a55b19246
ms.date: 05/02/2018
ms.keywords: NdisCancelOidRequest, NdisCancelOidRequest function [Network Drivers Starting with Windows Vista], ndis/NdisCancelOidRequest, ndis_request_ref_5f7f8a9a-f773-4ca8-aba3-21fe74431e0c.xml, netvista.ndiscanceloidrequest
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
-	NdisCancelOidRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisCancelOidRequest function


## -description


Protocol drivers call the 
  <b>NdisCancelOidRequest</b> function to cancel a previous request to the underlying drivers.


## -parameters




### -param NdisBindingHandle [in]

The handle returned by the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a> function that
     identifies the target adapter on the binding.


### -param RequestId [in]

A cancellation identifier for the request. This identifier specifies the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structures that are being
     canceled.


## -returns



None




## -remarks



Protocol drivers call this function to cancel a previously issued request. The request ID that is
    passed at the 
    <i>RequestId</i> parameter must match the request ID in the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure that was passed
    in the call to the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff563710">NdisOidRequest</a> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563710">NdisOidRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>
 

 

