---
UID: NF:ndis.NdisClOpenAddressFamilyEx
title: NdisClOpenAddressFamilyEx function (ndis.h)
description: The NdisClOpenAddressFamilyEx function registers an address family (AF) that is associated with a call manager for a connection-oriented client.
old-location: netvista\ndisclopenaddressfamilyex.htm
tech.root: netvista
ms.assetid: 54170917-60b4-4d8f-bf92-df7d7dc0faee
ms.date: 05/02/2018
keywords: ["NdisClOpenAddressFamilyEx function"]
ms.keywords: NdisClOpenAddressFamilyEx, NdisClOpenAddressFamilyEx function [Network Drivers Starting with Windows Vista], condis_client_ref_6590ccca-3e48-4f83-a7d0-66ce9b6b1eef.xml, ndis/NdisClOpenAddressFamilyEx, netvista.ndisclopenaddressfamilyex
f1_keywords:
 - "ndis/NdisClOpenAddressFamilyEx"
 - "NdisClOpenAddressFamilyEx"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Protocol_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisClOpenAddressFamilyEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisClOpenAddressFamilyEx function


## -description


The 
  <b>NdisClOpenAddressFamilyEx</b> function registers an address family (AF) that is associated with a call
  manager for a connection-oriented client.


## -parameters




### -param NdisBindingHandle [in]

The handle that 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> returns and that
     identifies the target network interface card (NIC) or the virtual adapter of the next-lower driver that
     the caller is bound to.


### -param AddressFamily [in]

A pointer to a 
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff545368(v=vs.85)">CO_ADDRESS_FAMILY</a> structure that describes
     the call manager and AF to be opened. 
     

This pointer is an input parameter to the client's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_af_register_notify">
     ProtocolCoAfRegisterNotify</a> function, which calls 
     <b>NdisClOpenAddressFamilyEx</b>.


### -param ClientAfContext [in]

The handle to a caller-supplied resident context area in which the client maintains state for this
     AF after the AF has been opened. NDIS passes this handle back to the client in all subsequent calls
     concerning this AF if the call to 
     <b>NdisClOpenAddressFamilyEx</b> succeeds.


### -param NdisAfHandle [out]

A pointer to a caller-supplied variable in which 
     <b>NdisClOpenAddressFamilyEx</b> returns a handle that represents the newly opened address family.


## -returns



When 
     <b>NdisClOpenAddressFamilyEx</b> returns anything other than NDIS_STATUS_PENDING, the client should make
     an internal call to its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_open_af_complete_ex">
     ProtocolClOpenAfCompleteEx</a> function. Otherwise, NDIS calls the client's 
     <i>ProtocolClOpenAfCompleteEx</i> function when this operation is completed.




## -remarks



A CoNDIS client calls 
    <b>NdisClOpenAddressFamilyEx</b> from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_af_register_notify">
    ProtocolCoAfRegisterNotify</a> function, after the client checks the input buffer that is pointed to by
    the 
    <i>AddressFamily</i> parameter to determine whether the client recognizes the call manager and registered
    addresses. NDIS forwards the client's call of 
    <b>NdisClOpenAddressFamilyEx</b> to the call manager's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_open_af">ProtocolCmOpenAf</a> function, which
    ensures that the client has passed in a valid AF structure.

A successful call to 
    <b>NdisClOpenAddressFamilyEx</b> sets up communication from the client to a call manager. The client can
    then prepare to receive incoming calls by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclregistersap">NdisClRegisterSap</a> function. The client
    can also set up a virtual connection (VC) by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscocreatevc">NdisCoCreateVc</a> function so it can make an
    outgoing call by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclmakecall">NdisClMakeCall</a> function.

If the client's call to 
    <b>NdisClOpenAddressFamilyEx</b> fails, the client should call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisunbindadapter">NdisUnbindAdapter</a> function to request
    NDIS to release its binding to the underlying miniport adapter. Otherwise, the client must save the
    handle that is returned at the 
    <i>NdisAfHandle</i> parameter. This handle identifies the call manager to which subsequent requests concerning the given address
    family are directed. The client must treat this returned handle as an opaque variable, passing it
    unmodified and uninterpreted in subsequent 
    <b>Ndis<i>Xxx</i></b> function calls.

NDIS passes the pointer from the 
    <i>ClientAfContext</i> parameter to the client's registered 
    <i>ProtocolClXxx</i> functions in all subsequent calls that concern the AF until the client calls 
    <b>NdisClCloseAddressFamily</b> with the same 
    <i>NdisAfHandle</i> . After the AF is closed, the client can release or reuse the storage that it
    allocated at 
    <i>ClientAfContext</i> .




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff545368(v=vs.85)">CO_ADDRESS_FAMILY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatefromnpagedlookasidelist">
   NdisAllocateFromNPagedLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclcloseaddressfamily">NdisClCloseAddressFamily</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclmakecall">NdisClMakeCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclregistersap">NdisClRegisterSap</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscocreatevc">NdisCoCreateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisunbindadapter">NdisUnbindAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_open_af_complete_ex">ProtocolClOpenAfCompleteEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_open_af">ProtocolCmOpenAf</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_af_register_notify">ProtocolCoAfRegisterNotify</a>
 

 

