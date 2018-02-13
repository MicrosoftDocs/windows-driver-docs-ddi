---
UID: NF:ndis.NdisMCmCloseCallComplete
title: NdisMCmCloseCallComplete macro
author: windows-driver-content
description: NdisMCmCloseCallComplete returns the final status of a client's request, for which the MCM driver previously returned NDIS_STATUS_PENDING, to tear down a call.
old-location: netvista\ndismcmclosecallcomplete.htm
old-project: netvista
ms.assetid: 24477865-fb89-4078-99cb-1bf24249c7e2
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisMCmCloseCallComplete, netvista.ndismcmclosecallcomplete, condis_mcm_ref_78d6cea5-8d8c-49d4-ad57-c41eb63d3a4b.xml, ndis/NdisMCmCloseCallComplete, NdisMCmCloseCallComplete macro [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCmCloseCallComplete (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCmCloseCallComplete (NDIS   5.1)) in Windows XP.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	NdisMCmCloseCallComplete
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisMCmCloseCallComplete macro


## -description


<b>NdisMCmCloseCallComplete</b> returns the final status of a client's request, for which the MCM driver
  previously returned NDIS_STATUS_PENDING, to tear down a call.


## -syntax


````
VOID NdisMCmCloseCallComplete(
  [in]           NDIS_STATUS Status,
  [in]           NDIS_HANDLE NdisVcHandle,
  [in, optional] NDIS_HANDLE NdisPartyHandle
);
````


## -parameters




### -param _S_

TBD


### -param _VH_

TBD


### -param _PH_

TBD






#### - Status [in]

Specifies the final status of the client's request that the MCM driver close the connection,
     either NDIS_STATUS_SUCCESS or any caller-determined NDIS_STATUS_<i>XXX</i> except NDIS_STATUS_PENDING.


#### - NdisVcHandle [in]

Specifies the handle to the VC for the call. This handle was supplied by NDIS when the VC was
     originally created, whether by the MCM driver with 
     <a href="..\ndis\nf-ndis-ndismcmcreatevc.md">NdisMCmCreateVc</a> or as an input parameter
     to its 
     <a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a> function.


#### - NdisPartyHandle [in, optional]

Specifies either <b>NULL</b> if the 
     <i>NdisVcHandle</i> represents a point-to-point VC or the handle to the last remaining party on a
     multipoint connection, which the MCM driver obtained from its per-party state designated by the 
     <i>CallMgrPartyContext</i> passed as an input parameter to its 
     <a href="..\ndis\nc-ndis-protocol_cm_close_call.md">
     ProtocolCmCloseCall</a> function.


## -remarks



If an MCM driver's 
    <i>ProtocolCmCloseCall</i> function returns NDIS_STATUS_PENDING, it must call 
    <b>NdisMCmCloseCallComplete</b> subsequently to notify the client and NDIS that its attempt to break the
    connection has completed, whether successfully or with an error. A call to 
    <b>NdisMCmCloseCallComplete</b> causes NDIS to call the client's 
    <i>ProtocolClCloseCallComplete</i> function.

If it passes NDIS_STATUS_SUCCESS as the 
    <i>Status</i>, the MCM driver should consider the 
    <i>NdisVcHandle</i> (and 
    <i>NdisPartyHandle</i>, if any) unusable for transfers over the network as soon as it calls 
    <b>NdisMCmCloseCallComplete</b>. If the MCM driver originally created the VC, it should call 
    <a href="..\ndis\nf-ndis-ndismcmdeletevc.md">NdisMCmDeleteVc</a> with the same 
    <i>NdisVcHandle</i> that it just passed to 
    <b>NdisMCmCloseCallComplete</b>. If the client created this VC, the MCM driver can expect a call to its 
    <a href="..\ndis\nc-ndis-protocol_co_delete_vc.md">ProtocolCoDeleteVc</a> function with the
    
    <i>ProtocolVcContext</i>, designating its per-VC state in which it has stored the same 
    <i>NdisVcHandle</i>, as an input parameter.

Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmCloseCallComplete</b>. Stand-alone call managers, which register themselves with NDIS as
    protocol drivers, call 
    <b>NdisCmCloseCallComplete</b> instead.




## -see-also

<a href="..\ndis\nf-ndis-ndismcmdeactivatevc.md">NdisMCmDeactivateVc</a>



<a href="..\ndis\nc-ndis-protocol_co_delete_vc.md">ProtocolCoDeleteVc</a>



<a href="..\ndis\nf-ndis-ndisclclosecall.md">NdisClCloseCall</a>



<a href="..\ndis\nf-ndis-ndiscmclosecallcomplete.md">NdisCmCloseCallComplete</a>



<a href="..\ndis\nc-ndis-protocol_cl_close_call_complete.md">ProtocolClCloseCallComplete</a>



<a href="..\ndis\nf-ndis-ndismcmdeletevc.md">NdisMCmDeleteVc</a>



<a href="..\ndis\nf-ndis-ndismcmcreatevc.md">NdisMCmCreateVc</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMCmCloseCallComplete macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

