---
UID: NF:ndis.NdisCmOpenAddressFamilyComplete
title: NdisCmOpenAddressFamilyComplete function (ndis.h)
description: NdisCmOpenAddressFamilyComplete returns the final status of a stand-alone call manager's open of a given AF for a particular client after the call manager returned NDIS_STATUS_PENDING in response to that client's original open-AF request.
old-location: netvista\ndiscmopenaddressfamilycomplete.htm
tech.root: netvista
ms.assetid: eed57341-0b1a-4697-b05d-680bc17da796
ms.date: 05/02/2018
ms.keywords: NdisCmOpenAddressFamilyComplete, NdisCmOpenAddressFamilyComplete function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_0b6dfac0-905d-48a8-b547-85bfe047e8f1.xml, ndis/NdisCmOpenAddressFamilyComplete, netvista.ndiscmopenaddressfamilycomplete
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisCmOpenAddressFamilyComplete (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisCmOpenAddressFamilyComplete (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_CallManager_Function
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisCmOpenAddressFamilyComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisCmOpenAddressFamilyComplete function


## -description


<b>NdisCmOpenAddressFamilyComplete</b> returns the final status of a stand-alone call manager's open of a
  given AF for a particular client after the call manager returned NDIS_STATUS_PENDING in response to that
  client's original open-AF request.


## -parameters




### -param Status [in]

Specifies the final status of the open-AF operation, either NDIS_STATUS_SUCCESS or any
     CM-determined error NDIS_STATUS_
     <i>XXX</i> except NDIS_STATUS_PENDING.


### -param NdisAfHandle [in]

Specifies the NDIS-supplied handle that was input to the call manager's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cm_open_af">ProtocolCmOpenAf</a> function, which
     returned NDIS_STATUS_PENDING.


### -param CallMgrAfContext [in]

Specifies the handle to a caller-allocated resident context area in which the call manager
     maintains state about this client's open of the address family, including the 
     <i>NdisAfHandle</i>, if the open succeeded. If 
     <i>Status</i> is not NDIS_STATUS_SUCCESS, NDIS ignores this parameter.


## -returns



None




## -remarks



A stand-alone call manager must call 
    <b>NdisCmOpenAddressFamilyComplete</b> if its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cm_open_af">ProtocolCmOpenAf</a> function previously
    returned NDIS_STATUS_PENDING for the given 
    <i>NdisAfHandle</i> . The client, which initiated the pended open-AF operation with a call to 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisclopenaddressfamilyex">NdisClOpenAddressFamilyEx</a>,
    cannot carry out further connection-oriented operations on the same binding until 
    <b>NdisCmOpenAddressFamilyComplete</b> causes a call to that client's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cl_open_af_complete_ex">
    ProtocolClOpenAfCompleteEx</a> function.

If the caller of 
    <b>NdisCmOpenAddressFamilyComplete</b> sets 
    <i>Status</i> to NDIS_STATUS_SUCCESS, NDIS subsequently passes the given 
    <i>CallMgrAfContext</i> handle as an input parameter to all CM-supplied ProtocolCm<i>Xxx</i> and ProtocolCo<i>Xxx</i> functions that concern the client's open of the address family until the client closes the AF.
    The call manager should release or reuse any AF context area that it allocated before it passes a failure
    status to 
    <b>NdisCmOpenAddressFamilyComplete</b>.

For a successful open, the NDIS-supplied 
    <i>NdisAfHandle</i> represents an association between the call manager and client for the opened AF on a
    particular miniport driver to which the call manager and client are bound. Both protocol drivers must
    treat 
    <i>NdisAfHandle</i> as an opaque variable to be passed, unmodified and uninterpreted, in subsequent calls
    to NdisCl/Cm/CoXxx functions for which this handle is a required parameter. For a failed open, the call
    manager should consider the 
    <i>NdisAfHandle</i> invalid when 
    <b>NdisMCmOpenAddressFamilyComplete</b> returns control.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmOpenAddressFamilyComplete</b>. Connection-oriented miniport drivers that provide integrated
    call-management support must call 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismcmopenaddressfamilycomplete">
    NdisMCmOpenAddressFamilyComplete</a> instead.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisallocatefromnpagedlookasidelist">
   NdisAllocateFromNPagedLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisclopenaddressfamilyex">NdisClOpenAddressFamilyEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismcmopenaddressfamilycomplete">
   NdisMCmOpenAddressFamilyComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cl_open_af_complete_ex">ProtocolClOpenAfCompleteEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cm_open_af">ProtocolCmOpenAf</a>
 

 

