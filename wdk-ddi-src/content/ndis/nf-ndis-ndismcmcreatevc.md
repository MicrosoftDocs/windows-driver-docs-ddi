---
UID: NF:ndis.NdisMCmCreateVc
title: NdisMCmCreateVc function (ndis.h)
description: NdisMCmCreateVc sets up a connection endpoint on which an MCM driver can dispatch an incoming-call offer to a client.
old-location: netvista\ndismcmcreatevc.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisMCmCreateVc function"]
ms.keywords: NdisMCmCreateVc, NdisMCmCreateVc function [Network Drivers Starting with Windows Vista], condis_mcm_ref_eab0d24d-ee49-457d-9475-e4d7c3a50023.xml, ndis/NdisMCmCreateVc, netvista.ndismcmcreatevc
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCmCreateVc (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCmCreateVc (NDIS 5.1)) in   Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_MCM_Function
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
 - NdisMCmCreateVc
 - ndis/NdisMCmCreateVc
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisMCmCreateVc
---

# NdisMCmCreateVc function


## -description

<b>NdisMCmCreateVc</b> sets up a connection endpoint on which an MCM driver can dispatch an incoming-call
  offer to a client.

## -parameters

### -param MiniportAdapterHandle 

[in]
Specifies the NDIS-supplied handle originally input to 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>.

### -param NdisAfHandle 

[in]
Specifies the handle that identifies the client that is the target of an incoming call. The MCM
     driver obtained this handle as an input parameter to its 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_open_af">ProtocolCmOpenAf</a> function.

### -param MiniportVcContext 

[in]
Specifies the handle to a caller-supplied resident context area in which the MCM driver maintains
     state for this VC. NDIS passes this handle back to the MCM driver in all subsequent calls concerning
     this VC if the call to 
     <b>NdisMCmCreateVc</b> succeeds.

### -param NdisVcHandle 

[out]
Pointer to a caller-supplied variable that must be initialized to <b>NULL</b> before 
     <b>NdisMCmCreateVc</b> is called. On return from a successful call, this variable has been set to an
     NDIS-supplied handle for the newly created VC. The caller must save this handle for subsequent calls to
     connection-oriented 
     <b>Ndis<i>Xxx</i></b> functions concerning this VC.

## -returns

<b>NdisMCmCreateVc</b> can return one of the following:

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
NDIS created the VC successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
NDIS could not allocate sufficient memory to set up the VC.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
The given 
       <i>NdisAfHandle</i> is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_<i>XXX</i></b></dt>
</dl>
</td>
<td width="60%">
The client failed the creation of the VC for some reason, and NDIS has propagated the error
       status returned by its 
       <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a> function to
       the MCM driver.

</td>
</tr>
</table>

## -remarks

An MCM driver creates a VC with 
    <b>NdisMCmCreateVc</b> to represent an incoming offer of a connection from a remote node directed to a SAP
    that has already been registered with the MCM driver.

In the process of VC creation, NDIS supplies an 
    <i>NdisVcHandle</i> to the client and the MCM driver. This handle identifies the virtual connection for
    the client and miniport driver to which subsequent requests concerning the given VC are directed. Each
    driver must treat this VC handle as an opaque variable, passing it unmodified and uninterpreted in
    subsequent calls to certain connection-oriented NDIS library functions.

Usually, callers of 
    <b>NdisMCmCreateVc</b> store the returned 
    <i>NdisVcHandle</i> in the caller-allocated state area at 
    <i>MiniportVcContext</i> . NDIS passes an 
    <i>NdisVcHandle</i> as an input parameter to the 
    <i>ProtocolCoCreateVc</i> function of the appropriate client whenever an MCM driver creates a VC.

When an MCM driver processes the offer of an incoming call directed to one of its registered SAPs, it
    must call 
    <b>NdisMCmCreateVc</b> first. As a synchronous operation, NDIS calls the client's 
    <i>ProtocolCoCreateVc</i> function before 
    <b>NdisMCmCreateVc</b> returns control. If its call to 
    <b>NdisMCmCreateVc</b> succeeds, the MCM driver can proceed in notifying the appropriate client, passing
    the returned value at 
    <i>NdisVcHandle</i> to 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdispatchincomingcall">
    NdisMCmDispatchIncomingCall</a>.

The driver writer determines whether an MCM driver has an (internal) 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_create_vc">MiniportCoCreateVc</a> function that the
    driver calls in the context of setting up connections for outgoing and incoming calls.

Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmCreateVc</b>. Stand-alone call managers and clients, which register themselves with NDIS as
    protocol drivers, call 
    <b>NdisCoCreateVc</b> instead.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_create_vc">MiniportCoCreateVc</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatefromnpagedlookasidelist">
   NdisAllocateFromNPagedLookasideList</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclmakecall">NdisClMakeCall</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscocreatevc">NdisCoCreateVc</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdeletevc">NdisMCmDeleteVc</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdispatchincomingcall">NdisMCmDispatchIncomingCall</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_reg_sap">ProtocolCmRegisterSap</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a>
