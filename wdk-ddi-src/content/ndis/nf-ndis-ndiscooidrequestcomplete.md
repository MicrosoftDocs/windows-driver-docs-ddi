---
UID: NF:ndis.NdisCoOidRequestComplete
title: NdisCoOidRequestComplete function
author: windows-driver-content
description: The NdisCoOidRequestComplete function returns the final status of an OID request that a CoNDIS client's or stand-alone call manager's ProtocolCoOidRequest function previously returned NDIS_STATUS_PENDING for.
old-location: netvista\ndiscooidrequestcomplete.htm
old-project: netvista
ms.assetid: ba4a22a1-ad48-43f1-96f5-dee5d76e49cb
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisCoOidRequestComplete, NdisCoOidRequestComplete function [Network Drivers Starting with Windows Vista], condis_request_ref_29e0ae37-d6e6-4c75-b0fa-a6f84494f4a6.xml, ndis/NdisCoOidRequestComplete, netvista.ndiscooidrequestcomplete
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
req.ddi-compliance: Irql_Connection_Function
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
-	NdisCoOidRequestComplete
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisCoOidRequestComplete function


## -description


The 
  <b>NdisCoOidRequestComplete</b> function returns the final status of an OID request that a CoNDIS client's
  or stand-alone call manager's 
  <a href="https://msdn.microsoft.com/8247396f-8781-45da-aba1-a31a2a26a46f">ProtocolCoOidRequest</a> function
  previously returned NDIS_STATUS_PENDING for.


## -parameters




### -param NdisAfHandle [in]

An address family (AF) handle that NDIS passed to the client or stand-alone call manager's 
     <a href="https://msdn.microsoft.com/8247396f-8781-45da-aba1-a31a2a26a46f">
     ProtocolCoOidRequest</a> function.


### -param NdisVcHandle [in, optional]

A virtual connection (VC) handle that NDIS passed to the client or stand-alone call manager's 
     <i>ProtocolCoOidRequest</i> function. A <b>NULL</b> value for this parameter indicates that the request is not
     VC-specific. This parameter is <b>NULL</b> if the caller of the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff561711">NdisCoOidRequest</a> or 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563548">NdisMCmOidRequest</a> function specified a
     <b>NULL</b> VC handle.


### -param NdisPartyHandle [in, optional]

A party handle that NDIS passed to the client or stand-alone call manager's 
     <i>ProtocolCoOidRequest</i> function. A <b>NULL</b> value for this parameter indicates that the request is not
     party-specific. This parameter is <b>NULL</b> if the caller of the 
     <b>NdisCoOidRequest</b> or 
     <b>NdisMCmOidRequest</b> function specified a <b>NULL</b> party handle.


### -param OidRequest [in]

A pointer to a buffer that is formatted as an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure. The caller of
     the 
     <b>NdisCoOidRequest</b> or 
     <b>NdisMCmOidRequest</b> function supplied this buffer.


### -param Status [in]

The final status of the request operation, either NDIS_STATUS_SUCCESS, or any driver-determined
     NDIS_STATUS_<i>XXX</i> status value 
     except NDIS_STATUS_PENDING.


## -returns



None




## -remarks



A CoNDIS protocol driver that returns NDIS_STATUS_PENDING from its 
    <a href="https://msdn.microsoft.com/8247396f-8781-45da-aba1-a31a2a26a46f">ProtocolCoOidRequest</a> function must
    call 
    <b>NdisCoOidRequestComplete</b> after the protocol driver has finished the request operation.

After a driver calls 
    <b>NdisCoOidRequestComplete</b>, NDIS calls the 
    <a href="https://msdn.microsoft.com/16883c64-3cc6-4f50-8be7-7c58c422a717">
    ProtocolCoOidRequestComplete</a> function of the driver that originally called the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561711">NdisCoOidRequest</a> or 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff563548">NdisMCmOidRequest</a> function.

Only clients and stand-alone call managers, which register themselves with NDIS as protocol drivers,
    can call 
    <b>NdisCoOidRequestComplete</b>. Miniport call managers (MCMs) call the 
    <a href="https://msdn.microsoft.com/4c45be9f-3d07-4150-830a-3aa6d74531ff">
    NdisMCmOidRequestComplete</a> function or 
    <a href="https://msdn.microsoft.com/18242351-3dec-40df-b112-2335253903d2">
    NdisMCoOidRequestComplete</a> instead, depending on whether the MCM driver's 
    <a href="https://msdn.microsoft.com/8247396f-8781-45da-aba1-a31a2a26a46f">ProtocolCoOidRequest</a> or 
    <a href="https://msdn.microsoft.com/903bcdc5-9d42-4067-a054-057edc95ccf7">MiniportCoOidRequest</a> function,
    respectively, handled the client's request.




## -see-also




<a href="https://msdn.microsoft.com/903bcdc5-9d42-4067-a054-057edc95ccf7">MiniportCoOidRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561711">NdisCoOidRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563548">NdisMCmOidRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563551">NdisMCmOidRequestComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563568">NdisMCoOidRequestComplete</a>



<a href="https://msdn.microsoft.com/8247396f-8781-45da-aba1-a31a2a26a46f">ProtocolCoOidRequest</a>



<a href="https://msdn.microsoft.com/16883c64-3cc6-4f50-8be7-7c58c422a717">
   ProtocolCoOidRequestComplete</a>
 

 

