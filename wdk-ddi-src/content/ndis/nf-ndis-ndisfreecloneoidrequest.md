---
UID: NF:ndis.NdisFreeCloneOidRequest
title: NdisFreeCloneOidRequest function (ndis.h)
description: The NdisFreeCloneOidRequest function frees a cloned NDIS_OID_REQUEST structure.
old-location: netvista\ndisfreecloneoidrequest.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisFreeCloneOidRequest function"]
ms.keywords: NdisFreeCloneOidRequest, NdisFreeCloneOidRequest function [Network Drivers Starting with Windows Vista], ndis/NdisFreeCloneOidRequest, ndis_request_ref_450d80e2-3414-4c02-aca1-848c75f824a6.xml, netvista.ndisfreecloneoidrequest
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisFreeCloneOidRequest
 - ndis/NdisFreeCloneOidRequest
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisFreeCloneOidRequest
---

# NdisFreeCloneOidRequest function


## -description

The 
  <b>NdisFreeCloneOidRequest</b> function frees a cloned 
  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure.

## -parameters

### -param SourceHandle 

[in]
An NDIS handle that identifies a filter module or an intermediate driver's protocol
     binding.

### -param Request 

[in]
A pointer to the 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure that is to be
     freed.

## -remarks

An NDIS intermediate driver or filter driver calls 
    <b>NdisFreeCloneOidRequest</b> to free an NDIS_OID_REQUEST structure that was allocated by calling the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatecloneoidrequest">
    NdisAllocateCloneOidRequest</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatecloneoidrequest">NdisAllocateCloneOidRequest</a>
