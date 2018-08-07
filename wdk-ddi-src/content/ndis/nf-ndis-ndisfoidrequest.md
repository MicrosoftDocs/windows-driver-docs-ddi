---
UID: NF:ndis.NdisFOidRequest
title: NdisFOidRequest function
author: windows-driver-content
description: Filter drivers call the NdisFOidRequest function to forward an OID request to underlying drivers or to originate such a request.
old-location: netvista\ndisfoidrequest.htm
tech.root: netvista
ms.assetid: 8434bf2c-9c9a-49a1-bf88-b67b1eec721c
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: NdisFOidRequest, NdisFOidRequest function [Network Drivers Starting with Windows Vista], ndis/NdisFOidRequest, ndis_request_ref_b5034fc8-9122-4c87-b690-a6989c1592c1.xml, netvista.ndisfoidrequest
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
-	NdisFOidRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFOidRequest function


## -description


Filter drivers call the 
  <b>NdisFOidRequest</b> function to forward an OID request to underlying drivers or to originate such a
  request.


## -parameters




### -param NdisFilterHandle [in]

An NDIS handle that identifies a filter module. NDIS passed the handle to the filter driver in a
     call to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a> function.


### -param OidRequest [in]

A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure that specifies
     the operation requested with a given OID_<i>XXX</i> code. The structure can specify a query, set, or method request. For more information about
     OIDs, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566707">NDIS OIDs</a>.


## -returns



See the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563710">NdisOidRequest</a> function.




## -remarks



Filter drivers can originate OID requests to underlying drivers by calling 
    <b>NdisFOidRequest</b>.

Filter drivers can also filter OID requests that are originated by overlying drivers. NDIS calls the 
    <a href="https://msdn.microsoft.com/238bfa21-a971-4fe4-a774-6ba834efc3c5">FilterOidRequest</a> function to process
    each such request.

If 
    <b>NdisFOidRequest</b> returns <b>NDIS_STATUS_PENDING</b>, NDIS calls the 
    <a href="https://msdn.microsoft.com/2dba21d8-512b-4a1a-9cf9-0240c94a69a0">FilterOidRequestComplete</a> function after the underlying drivers complete the OID request.

If 
    <b>NdisFOidRequest</b> returns <b>NDIS_STATUS_SUCCESS</b>, it returns the results of a query request in the
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure at the 
    <i>OidRequest</i> parameter.

<b>NdisFOidRequest</b> can return <b>NDIS_STATUS_INVALID_PARAMETER</b> if the filter driver passes invalid values
    for the 
    <b>Type</b> and 
    <b>Size</b> fields in the 
    <b>Header</b> field of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure.

A driver can call 
    <b>NdisFOidRequest</b> when it is in the 
    <i>Restarting</i>, 
    <i>Running</i>, 
    <i>Pausing</i>, or 
    <i>Paused</i> state.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a>



<a href="https://msdn.microsoft.com/238bfa21-a971-4fe4-a774-6ba834efc3c5">FilterOidRequest</a>



<a href="https://msdn.microsoft.com/2dba21d8-512b-4a1a-9cf9-0240c94a69a0">FilterOidRequestComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563710">NdisOidRequest</a>
 

 

