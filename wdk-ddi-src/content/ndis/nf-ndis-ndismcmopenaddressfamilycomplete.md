---
UID: NF:ndis.NdisMCmOpenAddressFamilyComplete
title: NdisMCmOpenAddressFamilyComplete macro
author: windows-driver-content
description: NdisMCmOpenAddressFamilyComplete returns the final status of a client's request, for which the MCM driver's ProtocolCmOpenAf function returned NDIS_STATUS_PENDING, to open the MCM driver's address family.
old-location: netvista\ndismcmopenaddressfamilycomplete.htm
tech.root: netvista
ms.assetid: e2d6c7db-09b3-4e5a-a6da-607c67e03054
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: NdisMCmOpenAddressFamilyComplete, NdisMCmOpenAddressFamilyComplete macro [Network Drivers Starting with Windows Vista], condis_mcm_ref_b03ae7ee-6f52-4d98-a7ff-f8b5840b6472.xml, ndis/NdisMCmOpenAddressFamilyComplete, netvista.ndismcmopenaddressfamilycomplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisMCmOpenAddressFamilyComplete (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisMCmOpenAddressFamilyComplete (NDIS 5.1)) in Windows XP.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisMCmOpenAddressFamilyComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMCmOpenAddressFamilyComplete macro


## -description


<b>NdisMCmOpenAddressFamilyComplete</b> returns the final status of a client's request, for which the MCM
  driver's 
  <a href="https://msdn.microsoft.com/7422c205-bc41-4121-b430-ff9e6b49dc2e">ProtocolCmOpenAf</a> function returned
  NDIS_STATUS_PENDING, to open the MCM driver's address family.


## -parameters




### -param _S_

Specifies the final status of the client's request to open the AF, either NDIS_STATUS_SUCCESS or
     any caller-determined NDIS_STATUS_
     <i>XXX</i> except NDIS_STATUS_PENDING.

### -param _H_

Specifies the NDIS-supplied handle that was input to the MCM driver's 
     <i>ProtocolCmOpenAf</i> function, which returned NDIS_STATUS_PENDING.

### -param _C_

Specifies the handle to a caller-allocated resident context area, in which the MCM driver
     maintains state about this client's open of the address family, including the 
     <i>NdisAfHandle</i>, if the open succeeded. Otherwise, NDIS ignores this parameter.

## -remarks



An MCM driver must call 
    <b>NdisMCmOpenAddressFamilyComplete</b> if its 
    <a href="https://msdn.microsoft.com/7422c205-bc41-4121-b430-ff9e6b49dc2e">ProtocolCmOpenAf</a> function previously
    returned NDIS_STATUS_PENDING for the given 
    <i>NdisAfHandle</i> . The client, which initiated the pended open-AF operation with a call to 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561639">NdisClOpenAddressFamilyEx</a>,
    cannot carry out further connection-oriented operations on the same binding until 
    <b>NdisMCmOpenAddressFamilyComplete</b> causes a call to that client's 
    <a href="https://msdn.microsoft.com/03ddbbfd-8fe8-44b6-8d3e-12a7bf6f8f6b">
    ProtocolClOpenAfCompleteEx</a> function.

If the caller of 
    <b>NdisMCmOpenAddressFamilyComplete</b> sets 
    <i>Status</i> to NDIS_STATUS_SUCCESS, NDIS subsequently passes the given 
    <i>CallMgrAfContext</i> handle as an input parameter to all MCM driver-supplied ProtocolCm<i>Xxx</i> and ProtocolCo<i>Xxx</i> functions that concern the client's open of the address family until the client closes the AF.
    The MCM driver should release or reuse any AF context area that it allocated before it passes a failure
    status to 
    <b>NdisMCmOpenAddressFamilyComplete</b>.

For a successful open, the NDIS-supplied 
    <i>NdisAfHandle</i> represents an association between the MCM driver and client for the opened AF. Both
    NDIS drivers must treat 
    <i>NdisAfHandle</i> as an opaque variable to be passed, unmodified and uninterpreted, in subsequent calls
    to NdisCl/Co/MCm/MCoXxx functions for which this handle is a required parameter. For a failed open, the
    MCM driver should consider the 
    <i>NdisAfHandle</i> invalid when 
    <b>NdisMCmOpenAddressFamilyComplete</b> returns control.

Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmOpenAddressFamilyComplete</b>. Stand-alone call managers, which register themselves with NDIS
    as protocol drivers, call 
    <b>NdisCmOpenAddressFamilyComplete</b> instead.




## -see-also




<a href="https://msdn.microsoft.com/df690a05-359d-44f0-b063-4fc21d6c4d76">
   NdisAllocateFromNPagedLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561639">NdisClOpenAddressFamilyEx</a>



<a href="https://msdn.microsoft.com/eed57341-0b1a-4697-b05d-680bc17da796">
   NdisCmOpenAddressFamilyComplete</a>



<a href="https://msdn.microsoft.com/03ddbbfd-8fe8-44b6-8d3e-12a7bf6f8f6b">ProtocolClOpenAfCompleteEx</a>



<a href="https://msdn.microsoft.com/7422c205-bc41-4121-b430-ff9e6b49dc2e">ProtocolCmOpenAf</a>
 

 

