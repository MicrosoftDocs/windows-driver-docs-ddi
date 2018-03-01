---
UID: NF:ndis.NdisMCmModifyCallQoSComplete
title: NdisMCmModifyCallQoSComplete macro
author: windows-driver-content
description: NdisMCmModifyCallQoSComplete indicates the completion of the client's request, for which the MCM driver previously returned NDIS_STATUS_PENDING, to modify the quality of service on a VC.
old-location: netvista\ndismcmmodifycallqoscomplete.htm
old-project: netvista
ms.assetid: 66157bc7-8094-481f-8aae-a438031b61d0
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisMCmModifyCallQoSComplete, NdisMCmModifyCallQoSComplete macro [Network Drivers Starting with Windows Vista], condis_mcm_ref_4b742f65-7e96-4e8b-aa3d-64f9c90aa4be.xml, ndis/NdisMCmModifyCallQoSComplete, netvista.ndismcmmodifycallqoscomplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCmModifyCallQoSComplete   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCmModifyCallQoSComplete   (NDIS 5.1)) in Windows XP.
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
req.lib: ndis.h
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisMCmModifyCallQoSComplete
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMCmModifyCallQoSComplete macro


## -description


<b>NdisMCmModifyCallQoSComplete</b> indicates the completion of the client's request, for which the MCM
  driver previously returned NDIS_STATUS_PENDING, to modify the quality of service on a VC.


## -syntax


````
VOID NdisMCmModifyCallQoSComplete(
  [in] NDIS_STATUS         Status,
  [in] NDIS_HANDLE         NdisVcHandle,
  [in] PCO_CALL_PARAMETERS CallParameters
);
````


## -parameters




### -param _S_

TBD


### -param _H_

TBD


### -param _P_

TBD






#### - CallParameters [in]

Pointer to a structure of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a> specifying a QoS
     acceptable to the MCM driver if 
     <i>Status</i> is set to NDIS_STATUS_SUCCESS.


#### - NdisVcHandle [in]

Specifies the handle to the VC, obtained from the per-VC state designated by the 
     <i>CallMgrVcContext</i> passed in to the MCM driver's 
     <a href="..\ndis\nc-ndis-protocol_cm_modify_qos_call.md">
     ProtocolCmModifyCallQoS</a> function for this request.


#### - Status [in]

Specifies the final status of the client's request to modify the QoS on this VC, either
     NDIS_STATUS_SUCCESS or any caller-determined NDIS_STATUS_<i>XXX</i><u>except</u> NDIS_STATUS_PENDING.


## -remarks



A call to 
    <b>NdisMCmModifyCallQoSComplete</b> causes NDIS to call the client's 
    <a href="..\ndis\nc-ndis-protocol_cl_modify_call_qos_complete.md">
    ProtocolClModifyCallQoSComplete</a> function.

The MCM driver should call 
    <b>NdisMCmActivateVc</b> whenever it makes changes in the call parameters on an active VC.

Because the MCM driver can modify the client-supplied call parameters that were input to its 
    <i>ProtocolCmModifyCallQoS</i> function before it calls 
    <b>NdisMCmModifyCallQoSComplete</b>, the client's 
    <i>ProtocolClModifyCallQoSComplete</i> function examines the QoS to determine whether it is acceptable to
    the client. 
    <i>ProtocolClModifyCallQoSComplete</i> simply returns control if the client accepts the given call
    parameters. Otherwise, the client tears down the call.

Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmModifyCallQoSComplete</b>. Stand-alone call managers, which register themselves with NDIS as
    protocol drivers, call 
    <b>NdisCmModifyCallQoSComplete</b> instead.




## -see-also

<a href="..\ndis\nc-ndis-protocol_cm_modify_qos_call.md">ProtocolCmModifyCallQoS</a>



<a href="..\ndis\nf-ndis-ndisclmodifycallqos.md">NdisClModifyCallQoS</a>



<a href="..\ndis\nf-ndis-ndiscmmodifycallqoscomplete.md">NdisCmModifyCallQosComplete</a>



<a href="..\ndis\nc-ndis-protocol_cl_modify_call_qos_complete.md">
   ProtocolClModifyCallQoSComplete</a>



<a href="..\ndis\nf-ndis-ndismcmactivatevc.md">NdisMCmActivateVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMCmModifyCallQoSComplete macro%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

