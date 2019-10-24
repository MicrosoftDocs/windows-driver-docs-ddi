---
UID: NS:netdma._NET_DMA_CHANNEL_PARAMETERS
title: _NET_DMA_CHANNEL_PARAMETERS (netdma.h)
description: The NET_DMA_CHANNEL_PARAMETERS structure specifies the configuration parameters that a DMA provider driver should use to configure a DMA channel.
old-location: netvista\net_dma_channel_parameters.htm
tech.root: netvista
ms.assetid: 0d09a9e9-06c5-4026-9053-ac74a59509cc
ms.date: 05/02/2018
ms.keywords: "*PNET_DMA_CHANNEL_PARAMETERS, NET_DMA_CHANNEL_PARAMETERS, NET_DMA_CHANNEL_PARAMETERS structure [Network Drivers Starting with Windows Vista], NetDmaTransferStatusActive, NetDmaTransferStatusArmed, NetDmaTransferStatusHalted, NetDmaTransferStatusIdle, NetDmaTransferStatusSuspend, PNET_DMA_CHANNEL_PARAMETERS, PNET_DMA_CHANNEL_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NET_DMA_CHANNEL_PARAMETERS, netdma/NET_DMA_CHANNEL_PARAMETERS, netdma/PNET_DMA_CHANNEL_PARAMETERS, netdma_ref_021ebc64-529e-4588-b5ff-83ed04aa9478.xml, netvista.net_dma_channel_parameters"
ms.topic: struct
f1_keywords:
 - "netdma/NET_DMA_CHANNEL_PARAMETERS"
req.header: netdma.h
req.include-header: Netdma.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
req.target-min-winversvr: Windows Server 2008
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
- NET_DMA_CHANNEL_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NET_DMA_CHANNEL_PARAMETERS, *PNET_DMA_CHANNEL_PARAMETERS
---

# _NET_DMA_CHANNEL_PARAMETERS structure


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported in Windows 8 and later.</div><div> </div>The <b>NET_DMA_CHANNEL_PARAMETERS</b> structure specifies the configuration parameters that a DMA provider
  driver should use to configure a DMA channel.


## -struct-fields




### -field Revision

The revision number of this structure. 

For Windows 7 and Windows Server 2008 R2 and later, set this member to
     <b>NET_DMA_CHANNEL_PARAMETERS_REVISION_2</b>.

For Windows Vista and Windows Server 2008, set this member to
     <b>NET_DMA_CHANNEL_PARAMETERS_REVISION_1</b>.


### -field Size

The size, in bytes, of this structure. Set this member to 
     sizeof(<b>NET_DMA_CHANNEL_PARAMETERS</b>).


### -field Flags

A set of bits for flags that define DMA channel attributes. Set this member to zero. There are
     currently no flags defined.


### -field CompletionVirtualAddress

The virtual address of the memory location where the DMA engine can write the DMA transfer
     completion status. This virtual address is associated with the physical address that is specified in the     
     <b>CompletionPhysicalAddress</b> member.


### -field CompletionPhysicalAddress

The physical address of the memory location where the DMA engine can write the DMA transfer
     completion status. If the <b>NET_DMA_STATUS_UPDATE_ON_COMPLETION</b> flag is not set in the 
     <b>ControlFlags</b> member of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/ns-netdma-_net_dma_descriptor">NET_DMA_DESCRIPTOR</a> structure, 
     <b>CompletionPhysicalAddress</b> is not used. Otherwise, the completion status value at the specified
     address is a 64-bit wide combination of the physical address of the most recent DMA descriptor that the
     DMA engine processed and additional status information. 
     

The physical address of the DMA descriptor must be aligned to 64-bit boundaries. Therefore, the lower
     six bits of the address are available for other information. The DMA engine combines the following
     status values with the descriptor address by using a bitwise OR operation:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NetDmaTransferStatusActive"></a><a id="netdmatransferstatusactive"></a><a id="NETDMATRANSFERSTATUSACTIVE"></a><dl>
<dt><b><b>NetDmaTransferStatusActive</b></b></dt>
</dl>
</td>
<td width="60%">
The DMA transfer for the most recent DMA descriptor completed without errors, and the DMA engine
       has more descriptors to process.

</td>
</tr>
<tr>
<td width="40%"><a id="NetDmaTransferStatusIdle"></a><a id="netdmatransferstatusidle"></a><a id="NETDMATRANSFERSTATUSIDLE"></a><dl>
<dt><b><b>NetDmaTransferStatusIdle</b></b></dt>
</dl>
</td>
<td width="60%">
The DMA transfer for the last DMA descriptor in the linked list of descriptors completed without
       errors.

</td>
</tr>
<tr>
<td width="40%"><a id="NetDmaTransferStatusSuspend"></a><a id="netdmatransferstatussuspend"></a><a id="NETDMATRANSFERSTATUSSUSPEND"></a><dl>
<dt><b><b>NetDmaTransferStatusSuspend</b></b></dt>
</dl>
</td>
<td width="60%">
The DMA transfer for the most recent DMA descriptor completed without errors, and DMA transfers
       are suspended because the NetDMA interface called the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_suspend_handler">ProviderSuspendDma</a> function. The DMA
       engine will restart the transfer after the NetDMA interface calls the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_resume_handler">ProviderResumeDma</a> function.

</td>
</tr>
<tr>
<td width="40%"><a id="NetDmaTransferStatusHalted"></a><a id="netdmatransferstatushalted"></a><a id="NETDMATRANSFERSTATUSHALTED"></a><dl>
<dt><b><b>NetDmaTransferStatusHalted</b></b></dt>
</dl>
</td>
<td width="60%">
The DMA transfer for the most recent DMA transfer was aborted because of errors or because the
       NetDMA interface called the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_abort_handler">ProviderAbortDma</a> function.

</td>
</tr>
<tr>
<td width="40%"><a id="NetDmaTransferStatusArmed"></a><a id="netdmatransferstatusarmed"></a><a id="NETDMATRANSFERSTATUSARMED"></a><dl>
<dt><b><b>NetDmaTransferStatusArmed</b></b></dt>
</dl>
</td>
<td width="60%">
The DMA transfer for the first descriptor has not completed and the completed descriptor address
       is not valid.

</td>
</tr>
</table>
 


### -field ProcessorAffinityMask

A bitmap that indicates CPUs that are available for use with this DMA channel. Each bit in 
     <b>ProcessorAffinityMask</b> identifies a CPU. For example, setting bit 0 indicates CPU 0 can be used,
     setting bit 1 indicates CPU 1 can be used, and so on.


### -field ChannelPriority

A DMA channel priority value that represents the priority for the DMA channel relative to other
     DMA channels on the same DMA engine. A lower priority setting indicates a lower priority DMA channel. If
     this value indicates a higher priority than the hardware supports, the highest value that the hardware
     supports should be used. The Windows Vista NetDMA interface sets this member to zero.


### -field CpuNumber

The CPU number that is associated with the DMA channel. The DMA provider driver sets the value
     before it returns from the      
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_channel_allocate_handler">ProviderAllocateDmaChannel</a> function. The DMA engine uses this CPU for interrupt DPCs that are
     associated with the DMA channel. If the DMA engine and computer configuration support MSI-X, the
     interrupt should also be associated with the indicated CPU number, unless there was no MSI-X interrupt
     available for the indicated CPU.


### -field ProcessorAffinityMaskEx

The group number and a bitmap of the CPUs that this DMA channel could be associated with.


## -remarks



Before using a DMA channel, the NetDMA interface calls the     
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_channel_allocate_handler">ProviderAllocateDmaChannel</a> function of the DMA provider driver to allocate and initialize the DMA
    channel.

The NetDMA interface supplies a <b>NET_DMA_CHANNEL_PARAMETERS</b> structure at the 
    <i>ChannelParameters</i> parameter of 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_channel_allocate_handler">ProviderAllocateDmaChannel</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/ns-netdma-_net_dma_descriptor">NET_DMA_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_abort_handler">ProviderAbortDma</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_channel_allocate_handler">ProviderAllocateDmaChannel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_resume_handler">ProviderResumeDma</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_suspend_handler">ProviderSuspendDma</a>
 

 

