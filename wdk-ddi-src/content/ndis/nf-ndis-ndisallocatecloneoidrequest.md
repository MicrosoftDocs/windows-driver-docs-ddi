---
UID: NF:ndis.NdisAllocateCloneOidRequest
title: NdisAllocateCloneOidRequest function
author: windows-driver-content
description: The NdisAllocateCloneOidRequest function allocates memory for a new NDIS_OID_REQUEST structure and copies all the information from an existing NDIS_OID_REQUEST structure to the newly allocated structure.
old-location: netvista\ndisallocatecloneoidrequest.htm
old-project: netvista
ms.assetid: 426ff4f4-7924-4115-9f66-b4152e2ba5bb
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisAllocateCloneOidRequest, NdisAllocateCloneOidRequest function [Network Drivers Starting with Windows Vista], ndis/NdisAllocateCloneOidRequest, ndis_request_ref_323c05f2-8b33-40c1-a4d8-385a8b0d0015.xml, netvista.ndisallocatecloneoidrequest
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
-	NdisAllocateCloneOidRequest
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisAllocateCloneOidRequest function


## -description


The 
  <b>NdisAllocateCloneOidRequest</b> function allocates memory for a new 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure and copies all the
  information from an existing NDIS_OID_REQUEST structure to the newly allocated structure.


## -parameters




### -param SourceHandle [in]

An NDIS handle that identifies a filter module or an intermediate driver's protocol
     binding.


### -param OidRequest

TBD


### -param PoolTag [in]

A kernel pool tag. The tag is a string, delimited by single quotation marks, with as many as four
     characters, usually specified in reverse order.


### -param ClonedOidRequest

TBD




#### - CloneRequest [out]

A pointer to a pointer to an NDIS_OID_REQUEST structure. If NDIS returns NDIS_STATUS_SUCCESS, NDIS
     provides a pointer to the new, cloned NDIS_OID_REQUEST structure; otherwise, NDIS sets the pointer value
     to <b>NULL</b>.


#### - Request [in]

A pointer to an existing 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure from which NDIS
     copies the information to the newly allocated structure.


## -returns



<b>NdisAllocateClonedRequest</b> can return one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
NDIS successfully allocated an NDIS_OID_REQUEST structure. The 
       <i>CloneRequest</i> parameter contains a pointer to the NDIS_OID_REQUEST structure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The allocation request failed because the NDIS handle specified at 
       <i>SourceHandle</i> is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The allocation request failed because NDIS did not have sufficient resources to complete the
       allocation request.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
The driver failed to allocate the cloned structure for reasons other than those in the preceding
       list.

</td>
</tr>
</table>
 




## -remarks



To forward a request down to the underlying drivers, an NDIS intermediate driver or filter driver must
    call 
    <b>NdisAllocateCloneOidRequest</b> to allocate a cloned 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure. A filter driver
    or intermediate driver should not forward the original NDIS_OID_REQUEST structure to underlying
    drivers.

<b>NdisAllocateCloneOidRequest</b> allocates new memory and copies the data from an existing
    NDIS_OID_REQUEST structure to the new structure.

The driver must subsequently call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561845">NdisFreeCloneOidRequest</a> function
    to free the NDIS_OID_REQUEST structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561845">NdisFreeCloneOidRequest</a>
 

 

