---
UID: NF:ndis.NdisMCmCloseAddressFamilyComplete
title: NdisMCmCloseAddressFamilyComplete macro (ndis.h)
description: NdisMCmCloseAddressFamilyComplete returns the final status of a client's request, for which the MCM driver returned NDIS_STATUS_PENDING, to close the AF.
old-location: netvista\ndismcmcloseaddressfamilycomplete.htm
tech.root: netvista
ms.assetid: be551557-06db-4fc9-bdcb-030e621e205a
ms.date: 05/02/2018
keywords: ["NdisMCmCloseAddressFamilyComplete macro"]
ms.keywords: NdisMCmCloseAddressFamilyComplete, NdisMCmCloseAddressFamilyComplete macro [Network Drivers Starting with Windows Vista], condis_mcm_ref_beab4fb5-32b1-4188-9e6a-47f286386919.xml, ndis/NdisMCmCloseAddressFamilyComplete, netvista.ndismcmcloseaddressfamilycomplete
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisMCmCloseAddressFamilyComplete (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see         NdisMCmCloseAddressFamilyComplete (NDIS 5.1)) in Windows XP.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisMCmCloseAddressFamilyComplete
 - ndis/NdisMCmCloseAddressFamilyComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NdisMCmCloseAddressFamilyComplete
---

# NdisMCmCloseAddressFamilyComplete macro


## -description

<b>NdisMCmCloseAddressFamilyComplete</b> returns the final status of a client's request, for which the MCM
  driver returned NDIS_STATUS_PENDING, to close the AF.

## -parameters

### -param _S_

The caller sets this to NDIS_STATUS_SUCCESS.

### -param _H_

Specifies the NDIS-supplied handle passed to the MCM driver's 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_open_af">ProtocolCmOpenAf</a> function when this
     client originally opened the address family.

## -remarks

An MCM driver must call 
    <b>NdisMCmCloseAddressFamilyComplete</b> if its 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_close_af">ProtocolCmCloseAf</a> function previously
    returned NDIS_STATUS_PENDING for the given 
    <i>NdisAfHandle</i> . The client, which initiated the pended close-AF operation with a call to 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclcloseaddressfamily">NdisClCloseAddressFamily</a>, cannot
    release the resources it allocated to track communications on the AF until the MCM driver's call to 
    <b>NdisMCmCloseAddressFamilyComplete</b>.

A call to 
    <b>NdisMCmCloseAddressFamilyComplete</b> causes NDIS to call the client's 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_close_af_complete">
    ProtocolClCloseAfComplete</a> function.

The MCM driver cannot subsequently use the 
    <i>NdisAfHandle</i>, which is invalid for the MCM driver when 
    <b>NdisMCmCloseAddressFamilyComplete</b> returns control.

Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmCloseAddressFamilyComplete</b>. Stand-alone call managers, which register themselves with NDIS
    as protocol drivers, call 
    <b>NdisCmCloseAddressFamilyComplete</b> instead.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclcloseaddressfamily">NdisClCloseAddressFamily</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmcloseaddressfamilycomplete">
   NdisCmCloseAddressFamilyComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_close_af_complete">ProtocolClCloseAfComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_close_af">ProtocolCmCloseAf</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_open_af">ProtocolCmOpenAf</a>