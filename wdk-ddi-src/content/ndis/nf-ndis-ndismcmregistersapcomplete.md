---
UID: NF:ndis.NdisMCmRegisterSapComplete
title: NdisMCmRegisterSapComplete macro (ndis.h)
description: NdisMCmRegisterSapComplete returns the final status of a client's request, for which the MCM driver's ProtocolCmRegisterSap function previously returned NDIS_STATUS_PENDING, to register a SAP.
old-location: netvista\ndismcmregistersapcomplete.htm
tech.root: netvista
ms.assetid: 53f94e25-ca6c-4230-8447-d36774322dc7
ms.date: 05/02/2018
ms.keywords: NdisMCmRegisterSapComplete, NdisMCmRegisterSapComplete macro [Network Drivers Starting with Windows Vista], condis_mcm_ref_4b7dfebf-1828-41cd-9645-0fc6774cc9a8.xml, ndis/NdisMCmRegisterSapComplete, netvista.ndismcmregistersapcomplete
ms.topic: macro
f1_keywords:
 - "ndis/NdisMCmRegisterSapComplete"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCmRegisterSapComplete   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCmRegisterSapComplete   (NDIS 5.1)) in Windows XP.
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
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- NdisMCmRegisterSapComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMCmRegisterSapComplete macro


## -description


<b>NdisMCmRegisterSapComplete</b> returns the final status of a client's request, for which the MCM driver's
  
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_reg_sap">ProtocolCmRegisterSap</a> function
  previously returned NDIS_STATUS_PENDING, to register a SAP.


## -parameters




### -param _S_

Specifies the final status for the client's original request to register the SAP, either
     NDIS_STATUS_SUCCESS or any caller-determined NDIS_STATUS_<i>XXX</i><u>except</u> NDIS_STATUS_PENDING.

### -param _H_

Specifies the NDIS-supplied handle to the SAP if the registration is successful. The call manager
     obtained this handle as an input parameter to its 
     <i>ProtocolCmRegisterSap</i> function.


### -param _C_

Specifies the handle to a caller-supplied resident context area in which the MCM driver maintains
     state for this SAP if the registration is successful. If so, NDIS passes this handle back to the to the
     MCM driver in all subsequent calls concerning this SAP. If 
     <i>Status</i> is set to something other than NDIS_STATUS_SUCCESS, NDIS ignores this parameter.


## -remarks



An MCM driver must call 
    <b>NdisMCmRegisterSapComplete</b> if its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_reg_sap">ProtocolCmRegisterSap</a> function
    returned NDIS_STATUS_PENDING when it was called with the given 
    <i>NdisSapHandle</i> . The call to 
    <b>NdisMCmRegisterSapComplete</b> causes NDIS to call the client's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_register_sap_complete">
    ProtocolClRegisterSapComplete</a> function.

If the MCM driver sets 
    <i>Status</i> to anything other than NDIS_STATUS_SUCCESS, it should consider the 
    <i>NdisSapHandle</i> invalid when 
    <b>NdisMCmRegisterSapComplete</b> returns control. After failing a SAP registration, the CM can release or
    reuse the per-SAP context area, if any, that it already allocated. NDIS also releases its context for the
    SAP if the MCM driver fails the registration.

Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmRegisterSapComplete</b>. Stand-alone call managers, which register themselves with NDIS as
    protocol drivers, call 
    <b>NdisCmRegisterSapComplete</b> instead.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatefromnpagedlookasidelist">
   NdisAllocateFromNPagedLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclregistersap">NdisClRegisterSap</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmregistersapcomplete">NdisCmRegisterSapComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdispatchincomingcall">NdisMCmDispatchIncomingCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_register_sap_complete">
   ProtocolClRegisterSapComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_reg_sap">ProtocolCmRegisterSap</a>
 

 

