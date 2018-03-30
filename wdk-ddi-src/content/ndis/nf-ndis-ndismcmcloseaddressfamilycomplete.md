---
UID: NF:ndis.NdisMCmCloseAddressFamilyComplete
title: NdisMCmCloseAddressFamilyComplete macro
author: windows-driver-content
description: NdisMCmCloseAddressFamilyComplete returns the final status of a client's request, for which the MCM driver returned NDIS_STATUS_PENDING, to close the AF.
old-location: netvista\ndismcmcloseaddressfamilycomplete.htm
old-project: netvista
ms.assetid: be551557-06db-4fc9-bdcb-030e621e205a
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisMCmCloseAddressFamilyComplete, NdisMCmCloseAddressFamilyComplete macro [Network Drivers Starting with Windows Vista], condis_mcm_ref_beab4fb5-32b1-4188-9e6a-47f286386919.xml, ndis/NdisMCmCloseAddressFamilyComplete, netvista.ndismcmcloseaddressfamilycomplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisMCmCloseAddressFamilyComplete
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMCmCloseAddressFamilyComplete macro


## -description


<b>NdisMCmCloseAddressFamilyComplete</b> returns the final status of a client's request, for which the MCM
  driver returned NDIS_STATUS_PENDING, to close the AF.


## -parameters




### -param _S_

TBD


### -param _H_

TBD






#### - NdisAfHandle [in]

Specifies the NDIS-supplied handle passed to the MCM driver's 
     <a href="https://msdn.microsoft.com/7422c205-bc41-4121-b430-ff9e6b49dc2e">ProtocolCmOpenAf</a> function when this
     client originally opened the address family.


#### - Status [in]

The caller sets this to NDIS_STATUS_SUCCESS.


## -remarks



An MCM driver must call 
    <b>NdisMCmCloseAddressFamilyComplete</b> if its 
    <a href="https://msdn.microsoft.com/a7a02813-62e4-49c5-abb6-a90f4e092b9f">ProtocolCmCloseAf</a> function previously
    returned NDIS_STATUS_PENDING for the given 
    <i>NdisAfHandle</i> . The client, which initiated the pended close-AF operation with a call to 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561626">NdisClCloseAddressFamily</a>, cannot
    release the resources it allocated to track communications on the AF until the MCM driver's call to 
    <b>NdisMCmCloseAddressFamilyComplete</b>.

A call to 
    <b>NdisMCmCloseAddressFamilyComplete</b> causes NDIS to call the client's 
    <a href="https://msdn.microsoft.com/7597e124-34e4-4326-98b3-c65dbe90ae6f">
    ProtocolClCloseAfComplete</a> function.

The MCM driver cannot subsequently use the 
    <i>NdisAfHandle</i>, which is invalid for the MCM driver when 
    <b>NdisMCmCloseAddressFamilyComplete</b> returns control.

Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmCloseAddressFamilyComplete</b>. Stand-alone call managers, which register themselves with NDIS
    as protocol drivers, call 
    <b>NdisCmCloseAddressFamilyComplete</b> instead.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561626">NdisClCloseAddressFamily</a>



<a href="https://msdn.microsoft.com/1aeb2ca5-8c56-4a78-8cd5-a178efa9b014">
   NdisCmCloseAddressFamilyComplete</a>



<a href="https://msdn.microsoft.com/7597e124-34e4-4326-98b3-c65dbe90ae6f">ProtocolClCloseAfComplete</a>



<a href="https://msdn.microsoft.com/a7a02813-62e4-49c5-abb6-a90f4e092b9f">ProtocolCmCloseAf</a>



<a href="https://msdn.microsoft.com/7422c205-bc41-4121-b430-ff9e6b49dc2e">ProtocolCmOpenAf</a>
 

 

