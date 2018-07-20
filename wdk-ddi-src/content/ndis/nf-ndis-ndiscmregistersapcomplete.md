---
UID: NF:ndis.NdisCmRegisterSapComplete
title: NdisCmRegisterSapComplete function
author: windows-driver-content
description: NdisCmRegisterSapComplete returns the final status of a client's request, for which the CM previously returned NDIS_STATUS_PENDING, to register a SAP.
old-location: netvista\ndiscmregistersapcomplete.htm
tech.root: netvista
ms.assetid: 0419bbf5-02aa-482f-9e2c-a435302751c4
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: NdisCmRegisterSapComplete, NdisCmRegisterSapComplete function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_1f862b68-070b-40d3-8edd-3830195af73c.xml, ndis/NdisCmRegisterSapComplete, netvista.ndiscmregistersapcomplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisCmRegisterSapComplete (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisCmRegisterSapComplete (NDIS   5.1)) in Windows XP.
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisCmRegisterSapComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisCmRegisterSapComplete function


## -description


<b>NdisCmRegisterSapComplete</b> returns the final status of a client's request, for which the CM previously
  returned NDIS_STATUS_PENDING, to register a SAP.


## -parameters




### -param Status [in]

Specifies the final status of the client's original request to register the SAP, either
     NDIS_STATUS_SUCCESS or any CM-determined NDIS_STATUS_<i>XXX</i> except NDIS_STATUS_PENDING.


### -param NdisSapHandle [in]

Specifies the NDIS-supplied handle to the SAP if the registration is successful. The call manager
     obtained this handle as an input parameter to its 
     <a href="https://msdn.microsoft.com/3e3e7a0e-a8d2-40b2-895b-187d24867080">
     ProtocolCmRegisterSap</a> function.


### -param CallMgrSapContext [in]

Specifies the handle to a caller-supplied resident context area in which the CM maintains state
     for this SAP if the registration is successful. If so, NDIS passes this handle back to the CM in all
     subsequent calls concerning this SAP. If 
     <i>Status</i> is set to something other than NDIS_STATUS_SUCCESS, NDIS ignores this parameter.


## -returns



None




## -remarks



A stand-alone call manager must call 
    <b>NdisCmRegisterSapComplete</b> if its 
    <a href="https://msdn.microsoft.com/3e3e7a0e-a8d2-40b2-895b-187d24867080">ProtocolCmRegisterSap</a> function
    returned NDIS_STATUS_PENDING when it was called with the given 
    <i>NdisSapHandle</i> . The call to 
    <b>NdisCmRegisterSapComplete</b> causes NDIS to call the client's 
    <a href="https://msdn.microsoft.com/b0a2a224-3353-4f20-b14f-ed5d633a6ead">
    ProtocolClRegisterSapComplete</a> function.

If the call manager sets 
    <i>Status</i> to anything other than NDIS_STATUS_SUCCESS, it should consider the 
    <i>NdisSapHandle</i> invalid as soon as it calls 
    <b>NdisCmRegisterSapComplete</b>. After failing a SAP registration, the CM can release or reuse the
    per-SAP context area that it allocated when 
    <b>NdisCmRegisterSapComplete</b> returns control. NDIS also releases its context for the SAP if the call
    manager fails the registration.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmRegisterSapComplete</b>. Connection-oriented miniport drivers that provide integrated
    call-management support call 
    <b>NdisMCmRegisterSapComplete</b>.




## -see-also




<a href="https://msdn.microsoft.com/df690a05-359d-44f0-b063-4fc21d6c4d76">
   NdisAllocateFromNPagedLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561648">NdisClRegisterSap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563557">NdisMCmRegisterSapComplete</a>



<a href="https://msdn.microsoft.com/b0a2a224-3353-4f20-b14f-ed5d633a6ead">
   ProtocolClRegisterSapComplete</a>



<a href="https://msdn.microsoft.com/3e3e7a0e-a8d2-40b2-895b-187d24867080">ProtocolCmRegisterSap</a>
 

 

