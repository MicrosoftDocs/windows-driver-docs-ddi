---
UID: NF:netdma.NetDmaPnPEventNotify
title: NetDmaPnPEventNotify function (netdma.h)
description: The NetDmaPnPEventNotify function indicates a power state change for a NetDMA provider device.
old-location: netvista\netdmapnpeventnotify.htm
tech.root: netvista
ms.assetid: a0f0fdbc-089c-4bfb-ba5f-eaff6042621c
ms.date: 05/02/2018
ms.keywords: NetDmaPnPEventNotify, NetDmaPnPEventNotify function [Network Drivers Starting with Windows Vista], netdma/NetDmaPnPEventNotify, netdma_ref_406452bc-e56a-47da-9e7a-09fb4aebe1eb.xml, netvista.netdmapnpeventnotify
ms.topic: function
req.header: netdma.h
req.include-header: Netdma.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NetDMA 2.0 and NetDMA 1.1 drivers in Windows Server 2008.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- netdma.h
api_name:
- NetDmaPnPEventNotify
product:
- Windows
targetos: Windows
req.typenames: 
---

# NetDmaPnPEventNotify function


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported 

in Windows 8 and later.</div><div> </div>The 
  <b>NetDmaPnPEventNotify</b> function indicates a power state change for a NetDMA provider device.


## -parameters




### -param NetDmaProviderHandle [in]

A handle that identifies a DMA provider. A DMA provider driver receives this handle from the
     NetDMA interface in a call to the 
     <a href="https://msdn.microsoft.com/35d70d0b-c1b9-433f-941d-6cb61ddf0b62">
     NetDmaRegisterProvider</a> function.


### -param PnPEvent [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568735">NET_DMA_PNP_NOTIFICATION</a> structure
     that specifies a NetDMA PnP and power management event.


## -returns



This function does not return a value.




## -remarks



NetDMA provider drivers call the 
    <b>NetDmaPnPEventNotify</b> function to indicate a power state change for a NetDMA provider device.

To send a power management notification to the NetDMA interface, NetDMA provider drivers call the 
    <b>NetDmaPnPEventNotify</b> function and provide a pointer to a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568735">NET_DMA_PNP_NOTIFICATION</a> structure
    at the 
    <i>PnPEvent</i> parameter.

A NetDMA provider driver calls 
    <b>NetDmaPnPEventNotify</b> at IRQL = PASSIVE_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568735">NET_DMA_PNP_NOTIFICATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568336">NetDmaRegisterProvider</a>
 

 

