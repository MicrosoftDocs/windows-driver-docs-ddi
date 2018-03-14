---
UID: NF:ndis.NdisCmCloseAddressFamilyComplete
title: NdisCmCloseAddressFamilyComplete function
author: windows-driver-content
description: NdisCmCloseAddressFamilyComplete returns the final status of a client's request, for which the CM's ProtocolCmCloseAf function returned NDIS_STATUS_PENDING, to close the AF.
old-location: netvista\ndiscmcloseaddressfamilycomplete.htm
old-project: netvista
ms.assetid: 1aeb2ca5-8c56-4a78-8cd5-a178efa9b014
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisCmCloseAddressFamilyComplete, NdisCmCloseAddressFamilyComplete function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_e8f3c7fa-1a6a-4cf4-9c3c-78f036c2e912.xml, ndis/NdisCmCloseAddressFamilyComplete, netvista.ndiscmcloseaddressfamilycomplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	NdisCmCloseAddressFamilyComplete
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisCmCloseAddressFamilyComplete function


## -description


<b>NdisCmCloseAddressFamilyComplete</b> returns the final status of a client's request, for which the CM's 
  <a href="..\ndis\nc-ndis-protocol_cm_close_af.md">ProtocolCmCloseAf</a> function returned
  NDIS_STATUS_PENDING, to close the AF.


## -syntax


````
VOID NdisCmCloseAddressFamilyComplete(
  _In_ NDIS_STATUS Status,
  _In_ NDIS_HANDLE NdisAfHandle
);
````


## -parameters




### -param Status [in]

The call manager sets this to NDIS_STATUS_SUCCESS.


### -param NdisAfHandle [in]

Specifies the NDIS-supplied handle passed to the call manager's 
     <a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a> function when this
     client originally opened the address family.


## -returns



None




## -remarks



A stand-alone call manager must call 
    <b>NdisCmCloseAddressFamilyComplete</b> if its 
    <a href="..\ndis\nc-ndis-protocol_cm_close_af.md">ProtocolCmCloseAf</a> function previously
    returned NDIS_STATUS_PENDING for the given 
    <i>NdisAfHandle</i> . The client, which initiated the pended close-AF operation with a call to 
    <a href="..\ndis\nf-ndis-ndisclcloseaddressfamily.md">NdisClCloseAddressFamily</a>, cannot
    release the resources it allocated to track communications on the AF until the CM's call to 
    <b>NdisCmCloseAddressFamilyComplete</b> causes a call to that client's 
    <a href="..\ndis\nc-ndis-protocol_cl_close_af_complete.md">
    ProtocolClCloseAfComplete</a> function.

After a call to 
    <b>NdisCmCloseAddressFamilyComplete</b>, the call manager cannot subsequently use the 
    <i>NdisAfHandle</i>, which becomes invalid for the call manager as soon as this call occurs.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmCloseAddressFamilyComplete</b>. Connection-oriented miniport drivers that provide integrated
    call-management support must call 
    <b>NdisMCmCloseAddressFamilyComplete</b> instead.




## -see-also

<a href="..\ndis\nc-ndis-protocol_cl_close_af_complete.md">ProtocolClCloseAfComplete</a>



<a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a>



<a href="..\ndis\nf-ndis-ndismcmcloseaddressfamilycomplete.md">
   NdisMCmCloseAddressFamilyComplete</a>



<a href="..\ndis\nc-ndis-protocol_cm_close_af.md">ProtocolCmCloseAf</a>



<a href="..\ndis\nf-ndis-ndisclcloseaddressfamily.md">NdisClCloseAddressFamily</a>



 

 


