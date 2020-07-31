---
UID: NS:netdma._NET_DMA_PROVIDER_CHARACTERISTICS
title: _NET_DMA_PROVIDER_CHARACTERISTICS (netdma.h)
description: The NET_DMA_PROVIDER_CHARACTERISTICS structure specifies the characteristics for a NetDMA provider, including the entry points for the ProviderXxx functions.
old-location: netvista\net_dma_provider_characteristics.htm
tech.root: netvista
ms.assetid: 7ec6d449-fdc2-44d8-976b-5a1d23c76e7b
ms.date: 05/02/2018
keywords: ["_NET_DMA_PROVIDER_CHARACTERISTICS structure"]
ms.keywords: "*PNET_DMA_PROVIDER_CHARACTERISTICS, NET_DMA_PROVIDER_CHARACTERISTICS, NET_DMA_PROVIDER_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNET_DMA_PROVIDER_CHARACTERISTICS, PNET_DMA_PROVIDER_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NET_DMA_PROVIDER_CHARACTERISTICS, netdma/NET_DMA_PROVIDER_CHARACTERISTICS, netdma/PNET_DMA_PROVIDER_CHARACTERISTICS, netdma_ref_24841207-9eca-483b-9ee5-81e7f24b62e6.xml, netvista.net_dma_provider_characteristics"
f1_keywords:
 - "netdma/NET_DMA_PROVIDER_CHARACTERISTICS"
 - "NET_DMA_PROVIDER_CHARACTERISTICS"
req.header: netdma.h
req.include-header: Netdma.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NetDMA 2.0 drivers in Windows Server 2008. (Added FriendlyName   member.) Supported for NetDMA 1.1 drivers in Windows Server 2008. Supported for NetDMA 1.0 drivers in   Windows Server 2008 and Windows Vista.
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- netdma.h
api_name:
- NET_DMA_PROVIDER_CHARACTERISTICS
targetos: Windows
req.typenames: NET_DMA_PROVIDER_CHARACTERISTICS, *PNET_DMA_PROVIDER_CHARACTERISTICS
---

# _NET_DMA_PROVIDER_CHARACTERISTICS structure


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported in Windows 8 and later.</div><div> </div>The NET_DMA_PROVIDER_CHARACTERISTICS structure specifies the characteristics for a NetDMA provider,
  including the entry points for the 
  <i>ProviderXxx</i> functions.


## -struct-fields




### -field MajorVersion

The major version number of the DMA provider driver.


### -field MinorVersion

The minor version number of the DMA provider driver.


### -field Size

The size, in bytes, of this NET_DMA_PROVIDER_CHARACTERISTICS structure. Set this member to 
     sizeof(NET_DMA_PROVIDER_CHARACTERISTICS).


### -field Flags

DMA provider characteristics flags. NetDMA 1.0 and 1.1 drivers set this member to zero.
     

NetDMA 2.0 and later drivers can use the following flags.





#### NET_DMA_PROVIDER_CHARACTERISTICS_DCA_SUPPORTED

The NetDMA provider supports 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/network/direct-cache-access--dca-">Direct Cache Access (DCA)</a>.


### -field PhysicalDeviceObject

The physical device object (PDO) that is associated with the DMA provider. The Plug and Play (PnP)
     manager supplies a pointer to the PDO at the 
     <i>PhysicalDeviceObject</i> parameter to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a> routine.


### -field MaxDmaChannelCount

The maximum number of DMA channels that the DMA provider can support.


### -field SetDmaChannelCpuAffinity

The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_channels_cpu_affinity_handler">
     ProviderSetDmaChannelCpuAffinity</a> function.


### -field AllocateDmaChannel

The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_channel_allocate_handler">
     ProviderAllocateDmaChannel</a> function.


### -field FreeDmaChannel

The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_channel_free_handler">
     ProviderFreeDmaChannel</a> function.


### -field StartDma

The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_start_handler">ProviderStartDma</a> function.


### -field SuspendDma

The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_suspend_handler">ProviderSuspendDma</a> function. If this
     function is not supported, set this member to <b>NULL</b>.


### -field ResumeDma

The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_resume_handler">ProviderResumeDma</a> function. If this
     function is not supported, set this member to <b>NULL</b>.


### -field AbortDma

The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_abort_handler">ProviderAbortDma</a> function. If this
     function is not supported, set this member to <b>NULL</b>.


### -field AppendDma

The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_append_handler">ProviderAppendDma</a> function.


### -field ResetChannel

The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_reset_handler">ProviderResetChannel</a> function. If
     this function is not supported, set this member to <b>NULL</b>.


### -field FriendlyName

A Unicode string that represents the user-readable description of the NetDMA provider
     driver.


## -remarks



To register a DMA provider, a DMA provider driver calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nf-netdma-netdmaregisterprovider">NetDmaRegisterProvider</a> function
    from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a> routine.

The DMA provider driver supplies a NET_DMA_PROVIDER_CHARACTERISTICS structure at the 
    <i>ProviderCharacteristics</i> parameter of 
    <b>NetDmaRegisterProvider</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nf-netdma-netdmaregisterprovider">NetDmaRegisterProvider</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_abort_handler">ProviderAbortDma</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_channel_allocate_handler">ProviderAllocateDmaChannel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_append_handler">ProviderAppendDma</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_channel_free_handler">ProviderFreeDmaChannel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_reset_handler">ProviderResetChannel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_resume_handler">ProviderResumeDma</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_channels_cpu_affinity_handler">
   ProviderSetDmaChannelCpuAffinity</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_start_handler">ProviderStartDma</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_suspend_handler">ProviderSuspendDma</a>
 

 

