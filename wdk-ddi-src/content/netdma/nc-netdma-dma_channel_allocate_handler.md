---
UID: NC:netdma.DMA_CHANNEL_ALLOCATE_HANDLER
title: DMA_CHANNEL_ALLOCATE_HANDLER
author: windows-driver-content
description: The ProviderAllocateDmaChannel function allocates a DMA channel.
old-location: netvista\providerallocatedmachannel.htm
old-project: netvista
ms.assetid: 42bc0e08-3d85-424f-aaa4-4df788d3706a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.providerallocatedmachannel, ProviderAllocateDmaChannel callback function [Network Drivers Starting with Windows Vista], ProviderAllocateDmaChannel, DMA_CHANNEL_ALLOCATE_HANDLER, DMA_CHANNEL_ALLOCATE_HANDLER, netdma/ProviderAllocateDmaChannel, netdma_ref_6f33588b-3234-4522-9ee6-3f56f3cd7be9.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: netdma.h
req.include-header: Netdma.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NetDMA 1.0 drivers in Windows Vista.
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	netdma.h
apiname:
-	ProviderAllocateDmaChannel
product: Windows
targetos: Windows
req.typenames: MIRACAST_DRIVER_INTERFACE, *PMIRACAST_DRIVER_INTERFACE
---

# DMA_CHANNEL_ALLOCATE_HANDLER callback


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported 

in Windows 8 and later.</div><div> </div>The 
  <i>ProviderAllocateDmaChannel</i> function allocates a DMA channel.


## -prototype


````
DMA_CHANNEL_ALLOCATE_HANDLER ProviderAllocateDmaChannel;

NTSTATUS ProviderAllocateDmaChannel(
  _In_  PVOID                       ProviderContext,
  _In_  PNET_DMA_CHANNEL_PARAMETERS ChannelParameters,
  _In_  PVOID                       NetDmaChannelHandle,
  _Out_ PVOID                       *pProviderChannelContext
)
{ ... }
````


## -parameters




### -param ProviderContext [in]

A pointer that identifies a DMA provider's context area. The DMA provider driver passes this
     handle to the NetDMA interface in a call to the 
     <a href="..\netdma\nf-netdma-netdmaregisterprovider.md">
     NetDmaRegisterProvider</a> function.


### -param ChannelParameters [in]

A pointer to a 
     <a href="..\netdma\ns-netdma-_net_dma_channel_parameters.md">
     NET_DMA_CHANNEL_PARAMETERS</a> structure that defines the configuration parameters for the DMA
     channel.


### -param NetDmaChannelHandle [in]

A handle that identifies the DMA channel. Provider drivers pass this handle to 
     <b>NetDma<i>Xxx</i></b> functions to identify the DMA channel.


### -param *pProviderChannelContext [out]

A pointer to a value that is a pointer to a DMA provider's context area for the DMA channel. The
     DMA provider driver allocates this context area before returning from 
     <i>ProviderAllocateDmaChannel</i>. NetDMA passes the context area pointer to 
     <i>ProviderXxx</i> functions that require a provider channel context.


## -returns



<i>ProviderAllocateDmaChannel</i> returns one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The operation failed because of insufficient resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The operation failed for unspecified reasons.

</td>
</tr>
</table>
 




## -remarks



The NetDMA interface calls a DMA provider driver's 
    <i>ProviderAllocateDmaChannel</i> function to allocate a DMA channel. The NetDMA interface calls 
    <i>ProviderAllocateDmaChannel</i> before it uses a DMA channel.

The DMA provider driver attempts to allocate a DMA channel with an interrupt CPU affinity that matches
    a bit that is specified in the 
    <b>ProcessorAffinityMask</b> member of the 
    <a href="..\netdma\ns-netdma-_net_dma_channel_parameters.md">
    NET_DMA_CHANNEL_PARAMETERS</a> structure at the 
    <i>ChannelParameters</i> parameter. If MSI-X is not supported or MSI-X is supported but a DMA channel with
    a matching interrupt CPU affinity is not available, the DMA provider driver allocates any available DMA
    channel and calls the 
    <a href="..\ntddk\nf-ntddk-kesettargetprocessordpc.md">KeSetTargetProcessorDpc</a> routine to
    set the target CPU of the interrupt DPC to match one of the specified affinity mask bits.

The DMA provider always driver returns the CPU number that it associated with the interrupt DPC for
    the DMA channel to the NetDMA interface in the 
    <b>CpuNumber</b> member of the NET_DMA_CHANNEL_PARAMETERS structure.

The DMA provider driver provides a pointer to a block of driver-allocated context information at the 
    <i>pProviderChannelContext</i> parameter of 
    <i>ProviderAllocateDmaChannel</i>. This context area stores information about the DMA channel. The NetDMA
    interface passes the context information in subsequent calls to 
    <i>ProviderXxx</i> functions that require a DMA channel context.

When the NetDMA interface calls 
    <i>ProviderAllocateDmaChannel</i>, it provides a handle at the 
    <i>NetDmaChannelHandle</i> parameter. The DMA provider driver uses this handle in subsequent calls to 
    <b>NetDma<i>Xxx</i></b> functions that are associated with the DMA channel.

The NetDMA interface calls the 
    <a href="..\netdma\nc-netdma-dma_channel_free_handler.md">ProviderFreeDmaChannel</a> function to
    free a previously allocated DMA channel.

NetDMA calls 
    <i>ProviderAllocateDmaChannel</i> at IRQL &lt;= DISPATCH_LEVEL.




## -see-also

<a href="..\netdma\nc-netdma-dma_channel_free_handler.md">ProviderFreeDmaChannel</a>



<a href="..\ntddk\nf-ntddk-kesettargetprocessordpc.md">KeSetTargetProcessorDpc</a>



<a href="..\netdma\ns-netdma-_net_dma_channel_parameters.md">NET_DMA_CHANNEL_PARAMETERS</a>



<a href="..\netdma\nf-netdma-netdmaregisterprovider.md">NetDmaRegisterProvider</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DMA_CHANNEL_ALLOCATE_HANDLER callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

