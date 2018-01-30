---
UID: NS:netdma._NET_DMA_PROVIDER_CHARACTERISTICS
title: "_NET_DMA_PROVIDER_CHARACTERISTICS"
author: windows-driver-content
description: The NET_DMA_PROVIDER_CHARACTERISTICS structure specifies the characteristics for a NetDMA provider, including the entry points for the ProviderXxx functions.
old-location: netvista\net_dma_provider_characteristics.htm
old-project: netvista
ms.assetid: 7ec6d449-fdc2-44d8-976b-5a1d23c76e7b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.net_dma_provider_characteristics, PNET_DMA_PROVIDER_CHARACTERISTICS, netdma_ref_24841207-9eca-483b-9ee5-81e7f24b62e6.xml, *PNET_DMA_PROVIDER_CHARACTERISTICS, netdma/PNET_DMA_PROVIDER_CHARACTERISTICS, PNET_DMA_PROVIDER_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], NET_DMA_PROVIDER_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], _NET_DMA_PROVIDER_CHARACTERISTICS, netdma/NET_DMA_PROVIDER_CHARACTERISTICS, NET_DMA_PROVIDER_CHARACTERISTICS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	netdma.h
apiname:
-	NET_DMA_PROVIDER_CHARACTERISTICS
product: Windows
targetos: Windows
req.typenames: NET_DMA_PROVIDER_CHARACTERISTICS, *PNET_DMA_PROVIDER_CHARACTERISTICS
---

# _NET_DMA_PROVIDER_CHARACTERISTICS structure


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported in Windows 8 and later.</div><div> </div>The NET_DMA_PROVIDER_CHARACTERISTICS structure specifies the characteristics for a NetDMA provider,
  including the entry points for the 
  <i>ProviderXxx</i> functions.


## -syntax


````
typedef struct _NET_DMA_PROVIDER_CHARACTERISTICS {
  UCHAR                             MajorVersion;
  UCHAR                             MinorVersion;
  USHORT                            Size;
  ULONG                             Flags;
  PDEVICE_OBJECT                    PhysicalDeviceObject;
  ULONG                             MaxDmaChannelCount;
  DMA_CHANNELS_CPU_AFFINITY_HANDLER SetDmaChannelCpuAffinity;
  DMA_CHANNEL_ALLOCATE_HANDLER      AllocateDmaChannel;
  DMA_CHANNEL_FREE_HANDLER          FreeDmaChannel;
  DMA_START_HANDLER                 StartDma;
  DMA_SUSPEND_HANDLER               SuspendDma;
  DMA_RESUME_HANDLER                ResumeDma;
  DMA_ABORT_HANDLER                 AbortDma;
  DMA_APPEND_HANDLER                AppendDma;
  DMA_RESET_HANDLER                 ResetChannel;
  UNICODE_STRING                    FriendlyName;
} NET_DMA_PROVIDER_CHARACTERISTICS, *PNET_DMA_PROVIDER_CHARACTERISTICS;
````


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
       <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/direct-cache-access--dca-">Direct Cache Access (DCA)</a>.


### -field PhysicalDeviceObject

The physical device object (PDO) that is associated with the DMA provider. The Plug and Play (PnP)
     manager supplies a pointer to the PDO at the 
     <i>PhysicalDeviceObject</i> parameter to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routine.


### -field MaxDmaChannelCount

The maximum number of DMA channels that the DMA provider can support.


### -field SetDmaChannelCpuAffinity

The entry point for the 
     <mshelp:link keywords="netvista.providersetdmachannelcpuaffinity" tabindex="0"><b>
     ProviderSetDmaChannelCpuAffinity</b></mshelp:link> function.


### -field AllocateDmaChannel

The entry point for the 
     <mshelp:link keywords="netvista.providerallocatedmachannel" tabindex="0"><b>
     ProviderAllocateDmaChannel</b></mshelp:link> function.


### -field FreeDmaChannel

The entry point for the 
     <mshelp:link keywords="netvista.providerfreedmachannel" tabindex="0"><b>
     ProviderFreeDmaChannel</b></mshelp:link> function.


### -field StartDma

The entry point for the 
     <a href="..\netdma\nc-netdma-dma_start_handler.md">ProviderStartDma</a> function.


### -field SuspendDma

The entry point for the 
     <a href="..\netdma\nc-netdma-dma_suspend_handler.md">ProviderSuspendDma</a> function. If this
     function is not supported, set this member to <b>NULL</b>.


### -field ResumeDma

The entry point for the 
     <a href="..\netdma\nc-netdma-dma_resume_handler.md">ProviderResumeDma</a> function. If this
     function is not supported, set this member to <b>NULL</b>.


### -field AbortDma

The entry point for the 
     <a href="..\netdma\nc-netdma-dma_abort_handler.md">ProviderAbortDma</a> function. If this
     function is not supported, set this member to <b>NULL</b>.


### -field AppendDma

The entry point for the 
     <a href="..\netdma\nc-netdma-dma_append_handler.md">ProviderAppendDma</a> function.


### -field ResetChannel

The entry point for the 
     <a href="..\netdma\nc-netdma-dma_reset_handler.md">ProviderResetChannel</a> function. If
     this function is not supported, set this member to <b>NULL</b>.


### -field FriendlyName

A Unicode string that represents the user-readable description of the NetDMA provider
     driver.


## -remarks


To register a DMA provider, a DMA provider driver calls the 
    <a href="..\netdma\nf-netdma-netdmaregisterprovider.md">NetDmaRegisterProvider</a> function
    from its 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routine.

The DMA provider driver supplies a NET_DMA_PROVIDER_CHARACTERISTICS structure at the 
    <i>ProviderCharacteristics</i> parameter of 
    <b>NetDmaRegisterProvider</b>.



## -see-also

<a href="..\netdma\nc-netdma-dma_channel_free_handler.md">ProviderFreeDmaChannel</a>

<a href="..\netdma\nc-netdma-dma_start_handler.md">ProviderStartDma</a>

<a href="..\netdma\nf-netdma-netdmaregisterprovider.md">NetDmaRegisterProvider</a>

<a href="..\netdma\nc-netdma-dma_resume_handler.md">ProviderResumeDma</a>

<a href="..\netdma\nc-netdma-dma_channel_allocate_handler.md">ProviderAllocateDmaChannel</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a>

<a href="..\netdma\nc-netdma-dma_append_handler.md">ProviderAppendDma</a>

<mshelp:link keywords="netvista.providersetdmachannelcpuaffinity" tabindex="0"><b>
   ProviderSetDmaChannelCpuAffinity</b></mshelp:link>

<a href="..\netdma\nc-netdma-dma_reset_handler.md">ProviderResetChannel</a>

<a href="..\netdma\nc-netdma-dma_suspend_handler.md">ProviderSuspendDma</a>

<a href="..\netdma\nc-netdma-dma_abort_handler.md">ProviderAbortDma</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NET_DMA_PROVIDER_CHARACTERISTICS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

