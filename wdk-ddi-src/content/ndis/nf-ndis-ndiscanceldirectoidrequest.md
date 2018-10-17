---
UID: NF:ndis.NdisCancelDirectOidRequest
title: NdisCancelDirectOidRequest function
author: windows-driver-content
description: Protocol drivers call the NdisCancelDirectOidRequest function to cancel a previous direct OID request to the underlying drivers.
old-location: netvista\ndiscanceldirectoidrequest.htm
tech.root: netvista
ms.assetid: bfccd901-9ce7-4873-ba9a-0e4718fd7d19
ms.date: 5/2/2018
ms.keywords: NdisCancelDirectOidRequest, NdisCancelDirectOidRequest function [Network Drivers Starting with Windows Vista], ndis/NdisCancelDirectOidRequest, ndis_request_direct_ref_71cb0f66-b7f7-49b5-b006-ca50eff45bcb.xml, netvista.ndiscanceldirectoidrequest
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisCancelDirectOidRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisCancelDirectOidRequest function


## -description


Protocol drivers call the 
  <b>NdisCancelDirectOidRequest</b> function to cancel a previous direct OID request to the underlying
  drivers.


## -parameters




### -param NdisBindingHandle [in]

The handle that the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a> function returned
     that identifies the target miniport adapter on the binding.


### -param RequestId [in]

A cancellation identifier for the request. This identifier specifies the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structures that are being
     canceled.


## -returns



None




## -remarks



Protocol drivers call the 
    <b>NdisCancelDirectOidRequest</b> function to cancel a previously issued direct OID request. The request
    ID that is passed at the 
    <i>RequestId</i> parameter must match the request ID in the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure that was passed
    in the call to the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561746">NdisDirectOidRequest</a> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561746">NdisDirectOidRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>
 

 

