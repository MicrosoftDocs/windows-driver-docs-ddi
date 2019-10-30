---
UID: NF:ndis.NdisCmCloseAddressFamilyComplete
title: NdisCmCloseAddressFamilyComplete function (ndis.h)
description: NdisCmCloseAddressFamilyComplete returns the final status of a client's request, for which the CM's ProtocolCmCloseAf function returned NDIS_STATUS_PENDING, to close the AF.
old-location: netvista\ndiscmcloseaddressfamilycomplete.htm
tech.root: netvista
ms.assetid: 1aeb2ca5-8c56-4a78-8cd5-a178efa9b014
ms.date: 05/02/2018
ms.keywords: NdisCmCloseAddressFamilyComplete, NdisCmCloseAddressFamilyComplete function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_e8f3c7fa-1a6a-4cf4-9c3c-78f036c2e912.xml, ndis/NdisCmCloseAddressFamilyComplete, netvista.ndiscmcloseaddressfamilycomplete
ms.topic: function
f1_keywords:
 - "ndis/NdisCmCloseAddressFamilyComplete"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisCmCloseAddressFamilyComplete (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisCmCloseAddressFamilyComplete (NDIS 5.1)) in Windows XP.
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisCmCloseAddressFamilyComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisCmCloseAddressFamilyComplete function


## -description


<b>NdisCmCloseAddressFamilyComplete</b> returns the final status of a client's request, for which the CM's 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_close_af">ProtocolCmCloseAf</a> function returned
  NDIS_STATUS_PENDING, to close the AF.


## -parameters




### -param Status [in]

The call manager sets this to NDIS_STATUS_SUCCESS.


### -param NdisAfHandle [in]

Specifies the NDIS-supplied handle passed to the call manager's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_open_af">ProtocolCmOpenAf</a> function when this
     client originally opened the address family.


## -returns



None




## -remarks



A stand-alone call manager must call 
    <b>NdisCmCloseAddressFamilyComplete</b> if its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_close_af">ProtocolCmCloseAf</a> function previously
    returned NDIS_STATUS_PENDING for the given 
    <i>NdisAfHandle</i> . The client, which initiated the pended close-AF operation with a call to 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclcloseaddressfamily">NdisClCloseAddressFamily</a>, cannot
    release the resources it allocated to track communications on the AF until the CM's call to 
    <b>NdisCmCloseAddressFamilyComplete</b> causes a call to that client's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_close_af_complete">
    ProtocolClCloseAfComplete</a> function.

After a call to 
    <b>NdisCmCloseAddressFamilyComplete</b>, the call manager cannot subsequently use the 
    <i>NdisAfHandle</i>, which becomes invalid for the call manager as soon as this call occurs.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmCloseAddressFamilyComplete</b>. Connection-oriented miniport drivers that provide integrated
    call-management support must call 
    <b>NdisMCmCloseAddressFamilyComplete</b> instead.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclcloseaddressfamily">NdisClCloseAddressFamily</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmcloseaddressfamilycomplete">
   NdisMCmCloseAddressFamilyComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_close_af_complete">ProtocolClCloseAfComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_close_af">ProtocolCmCloseAf</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_open_af">ProtocolCmOpenAf</a>
 

 

