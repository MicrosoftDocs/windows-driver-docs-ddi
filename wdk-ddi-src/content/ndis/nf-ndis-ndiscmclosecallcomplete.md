---
UID: NF:ndis.NdisCmCloseCallComplete
title: NdisCmCloseCallComplete function (ndis.h)
description: NdisCmCloseCallComplete returns the final status of a client's request, for which the call manager previously returned NDIS_STATUS_PENDING, to tear down a call.
old-location: netvista\ndiscmclosecallcomplete.htm
tech.root: netvista
ms.assetid: caf248e0-ec9a-4c85-86f7-f35c715c6e39
ms.date: 05/02/2018
ms.keywords: NdisCmCloseCallComplete, NdisCmCloseCallComplete function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_9380a315-f44c-4f6d-914f-480408c8d804.xml, ndis/NdisCmCloseCallComplete, netvista.ndiscmclosecallcomplete
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisCmCloseCallComplete (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisCmCloseCallComplete (NDIS   5.1)) in Windows XP.
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
- NdisCmCloseCallComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisCmCloseCallComplete function


## -description


<b>NdisCmCloseCallComplete</b> returns the final status of a client's request, for which the call manager
  previously returned NDIS_STATUS_PENDING, to tear down a call.


## -parameters




### -param Status [in]

Specifies the final status of the client's request that the CM close the connection, either
     NDIS_STATUS_SUCCESS or any CM-determined NDIS_STATUS_<i>XXX</i> except NDIS_STATUS_PENDING.


### -param NdisVcHandle [in]

Specifies the handle to the VC for the call. This handle was supplied by NDIS when the VC was
     originally created, whether by the call manager or client, with 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff561696">NdisCoCreateVc</a>. More recently, the call
     manager obtained this handle from its per-VC state designated by the 
     <i>CallMgrVcContext</i> passed as an input parameter to its 
     <a href="https://msdn.microsoft.com/b5307e1b-3905-4e43-a0b0-0068ba18ef0d">
     ProtocolCmCloseCall</a> function.


### -param NdisPartyHandle [in, optional]

Specifies either <b>NULL</b> if the 
     <i>NdisVcHandle</i> represents a point-to-point VC or the handle to the last remaining party on a
     multipoint connection, which the CM obtained from its per-party state designated by the 
     <i>CallMgrPartyContext</i> passed as an input parameter to its 
     <i>ProtocolCmCloseCall</i> function.


## -returns



None




## -remarks



If a stand-alone call manager's 
    <i>ProtocolCmCloseCall</i> function returns NDIS_STATUS_PENDING, the CM must call 
    <b>NdisCmCloseCallComplete</b> subsequently to notify the client and NDIS that its attempt to break the
    connection has completed, whether successfully or with an error. A call to 
    <b>NdisCmCloseCallComplete</b> causes NDIS to call the client's 
    <a href="https://msdn.microsoft.com/a7ba1ab2-04c9-45b5-a184-e1ad1448561a">
    ProtocolClCloseCallComplete</a> function.

If it passes NDIS_STATUS_SUCCESS as the 
    <i>Status</i>, the call manager should consider the 
    <i>NdisVcHandle</i> (and 
    <i>NdisPartyHandle</i>, if any) unusable for transfers over the network as soon as it calls 
    <b>NdisCmCloseCallComplete</b>. If the call manager originally created the VC, it should call 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561698">NdisCoDeleteVc</a> with the same 
    <i>NdisVcHandle</i> that it just passed to 
    <b>NdisCmCloseCallComplete</b>. If the client created this VC, the call manager can expect a call to its 
    <a href="https://msdn.microsoft.com/d761270f-bf77-441e-834c-9ac7fb3d350f">ProtocolCoDeleteVc</a> function with the    
    <i>ProtocolVcContext</i>, where it has the same 
    <i>NdisVcHandle</i>, as an input parameter.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmCloseCallComplete</b>. Connection-oriented miniport drivers that provide integrated
    call-management support call 
    <b>NdisMCmCloseCallComplete</b> instead.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561627">NdisClCloseCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561698">NdisCoDeleteVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562803">NdisMCmCloseCallComplete</a>



<a href="https://msdn.microsoft.com/a7ba1ab2-04c9-45b5-a184-e1ad1448561a">ProtocolClCloseCallComplete</a>



<a href="https://msdn.microsoft.com/d761270f-bf77-441e-834c-9ac7fb3d350f">ProtocolCoDeleteVc</a>
 

 

