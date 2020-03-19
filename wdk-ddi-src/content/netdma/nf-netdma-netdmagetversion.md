---
UID: NF:netdma.NetDmaGetVersion
title: NetDmaGetVersion function (netdma.h)
description: Note  The NetDMA interface is not supported in Windows 8 and later. The NetDmaGetVersion function returns the version of the NetDMA interface that the local computer supports.
old-location: netvista\netdmagetversion.htm
tech.root: netvista
ms.assetid: eec8ba30-0f9e-4487-ba0d-99587d97b44a
ms.date: 05/02/2018
keywords: ["NetDmaGetVersion function"]
ms.keywords: NetDmaGetVersion, NetDmaGetVersion function [Network Drivers Starting with Windows Vista], netdma/NetDmaGetVersion, netdma_ref_bb1adf18-d43d-4dc2-b780-1a1322014581.xml, netvista.netdmagetversion
f1_keywords:
 - "netdma/NetDmaGetVersion"
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
- NetDmaGetVersion
product:
- Windows
targetos: Windows
req.typenames: 
---

# NetDmaGetVersion function


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported 

in Windows 8 and later.</div><div> </div>

The 
  <b>NetDmaGetVersion</b> function returns the version of the NetDMA interface that the local computer
  supports.


## -returns



<b>NetDmaGetVersion</b> returns a UINT value that contains the major and minor version numbers as
     follows:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>High 16 bits</b></dt>
</dl>
</td>
<td width="60%">
The major version number of the NetDMA interface.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Low 16 bits</b></dt>
</dl>
</td>
<td width="60%">
The minor version of NetDMA interface.

</td>
</tr>
</table>
 




## -remarks



NetDMA provider drivers can call the 
    <b>NetDmaGetVersion</b> function to obtain the version of the NetDMA interface. A NetDMA provider must
    register as a NetDMA provider with a version equal to or lower than the NetDMA provider interface version
    that the local computer supports. The NetDMA provider driver specifies the major and minor version of the
    NetDMA provider in the 
    <b>MajorVersion</b> and 
    <b>MinorVersion</b> members of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/ns-netdma-_net_dma_provider_characteristics">
    NET_DMA_PROVIDER_CHARACTERISTICS</a> structure that it passes to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nf-netdma-netdmaregisterprovider">
    NetDmaRegisterProvider</a> function.

<div class="alert"><b>Note</b>  <b>NetDmaGetVersion</b> is not available in NetDMA version 1.0. To avoid using a function import that
    might stop the driver from loading, a NetDMA 1.1 or later provider driver must verify the presence of 
    <b>NetDmaGetVersion</b> before it calls 
    <b>NetDmaGetVersion</b>. To call 
    <b>NetDmaGetVersion</b>, first call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisgetroutineaddress">NdisGetRoutineAddress</a> function to
    get the entry point and then, if 
    <b>NetDmaGetVersion</b> is available, call 
    <b>NetDmaGetVersion</b> at the entry point that 
    <b>NdisGetRoutineAddress</b> provided. If the provider driver cannot get the address of 
    <b>NetDmaGetVersion</b>, the supported NetDMA interface must be version 1.0.</div>
<div> </div>
NetDMA provider drivers call 
    <b>NetDmaGetVersion</b> at IRQL = PASSIVE_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/ns-netdma-_net_dma_provider_characteristics">
   NET_DMA_PROVIDER_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisgetroutineaddress">NdisGetRoutineAddress</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nf-netdma-netdmaregisterprovider">NetDmaRegisterProvider</a>
 

 

