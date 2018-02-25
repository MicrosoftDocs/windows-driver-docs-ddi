---
UID: NC:netdma.DMA_START_HANDLER
title: DMA_START_HANDLER
author: windows-driver-content
description: The ProviderStartDma function starts a DMA transfer on the specified DMA channel.
old-location: netvista\providerstartdma.htm
old-project: netvista
ms.assetid: 0926e8c4-f2ca-401f-abe8-76aec359a1e2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: DMA_START_HANDLER, ProviderStartDma, ProviderStartDma callback function [Network Drivers Starting with Windows Vista], netdma/ProviderStartDma, netdma_ref_76be9ff2-b865-4516-ad7b-ab3951133f41.xml, netvista.providerstartdma
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: netdma.h
req.include-header: Netdma.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NetDMA 2.0 drivers in Windows Server 2008. Supported for NetDMA 1.1   drivers in Windows Server 2008. Supported for NetDMA 1.0 drivers in Windows Server 2008 and Windows   Vista.
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
-	ProviderStartDma
product: Windows
targetos: Windows
req.typenames: MIRACAST_DRIVER_INTERFACE, *PMIRACAST_DRIVER_INTERFACE
---

# DMA_START_HANDLER callback


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported 

in Windows 8 and later.</div><div> </div>The 
  <i>ProviderStartDma</i> function starts a DMA transfer on the specified DMA channel.


## -prototype


````
DMA_START_HANDLER ProviderStartDma;

NTSTATUS ProviderStartDma(
  _In_ PVOID               ProviderChannelContext,
  _In_ PNET_DMA_DESCRIPTOR DescriptorVirtualAddress,
  _In_ PHYSICAL_ADDRESS    DescriptorPhysicalAddress,
  _In_ ULONG               DescriptorCount
)
{ ... }
````


## -parameters




### -param ProviderChannelContext [in]

A pointer that identifies a DMA channel's context area. The DMA provider returned this handle to
     NetDMA at the location that is specified in the 
     <i>pProviderChannelContext</i> parameter of the 
     <a href="..\netdma\nc-netdma-dma_channel_allocate_handler.md">
     ProviderAllocateDmaChannel</a> function.


### -param DescriptorVirtualAddress [in]

A pointer to the virtual address of the first 
     <a href="..\netdma\ns-netdma-_net_dma_descriptor.md">NET_DMA_DESCRIPTOR</a> structure in a linked
     list of DMA descriptors. The corresponding physical address is specified at the 
     <i>DescriptorPhysicalAddress</i> parameter.


### -param DescriptorPhysicalAddress [in]

A pointer to the physical address of the first DMA descriptor in a linked list of DMA descriptors.
     The corresponding virtual address is specified at the 
     <i>DescriptorVirtualAddress</i> parameter.


### -param DescriptorCount [in]

The number of DMA descriptors at 
     <i>DescriptorVirtualAddress</i> .
     

<div class="alert"><b>Note</b>  NetDMA provider drivers prior to NetDMA version 2.0 can ignore the 
     <i>DescriptorCount</i> parameter. For NetDMA 2.0 and later versions, this parameter is the count of
     descriptors in the DMA operation.</div>
<div> </div>

## -returns



<i>ProviderStartDma</i> returns one of the following status values:

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
    <i>ProviderStartDma</i> function to start a DMA transfer. The NetDMA interface can call 
    <i>ProviderStartDma</i> at any time after a DMA channel is allocated. The NetDMA interface must call 
    <i>ProviderStartDma</i> after it calls the 
    <a href="..\netdma\nc-netdma-dma_abort_handler.md">ProviderAbortDma</a>, 
    <a href="..\netdma\nc-netdma-dma_reset_handler.md">ProviderResetChannel</a>, or 
    <a href="..\netdma\nc-netdma-dma_channel_allocate_handler.md">
    ProviderAllocateDmaChannel</a> function for a DMA channel.

The source of the DMA transfer is a linked list of DMA descriptors. The 
    <b>NextDescriptor</b> member of the 
    <a href="..\netdma\ns-netdma-_net_dma_descriptor.md">NET_DMA_DESCRIPTOR</a> structure at the 
    <i>DescriptorVirtualAddress</i> parameter contains the physical address of the next NET_DMA_DESCRIPTOR
    structure in the linked list.

<div class="alert"><b>Note</b>  In NetDMA 2.0 and later versions, the linked list of descriptors is not
    NULL-terminated. The 
    <b>NextDescriptor</b> member in the last descriptor in the linked list specifies the physical address of
    the 
    <a href="..\netdma\ns-netdma-_net_dma_descriptor.md">NET_DMA_DESCRIPTOR</a> structure that will be
    used in the subsequent call to the 
    <a href="..\netdma\nc-netdma-dma_append_handler.md">ProviderAppendDma</a> function. A NetDMA 2.0
    provider driver can cache the address in 
    <b>NextDescriptor</b> and use this address as the beginning of the linked list for the next Append
    operation.</div>
<div> </div>
To perform the start operation, the DMA provider must disregard the existing DMA descriptor list, if
    any, after it completes any processing on the current descriptor. The DMA provider must ignore the 
    <b>NextDescriptor</b> member in the current NET_DMA_DESCRIPTOR structure and load the descriptor that 
    <i>ProviderStartDma</i> specifies.

After 
    <i>ProviderStartDma</i> starts the initial DMA transfer, the NetDMA interface can call the 
    <a href="..\netdma\nc-netdma-dma_append_handler.md">ProviderAppendDma</a> function to append
    additional data to the transfer.

NetDMA calls 
    <i>ProviderStartDma</i> at IRQL &lt;= DISPATCH_LEVEL.




## -see-also

<a href="..\netdma\nc-netdma-dma_abort_handler.md">ProviderAbortDma</a>



<a href="..\netdma\nc-netdma-dma_append_handler.md">ProviderAppendDma</a>



<a href="..\netdma\ns-netdma-_net_dma_descriptor.md">NET_DMA_DESCRIPTOR</a>



<a href="..\netdma\nc-netdma-dma_reset_handler.md">ProviderResetChannel</a>



<a href="..\netdma\nc-netdma-dma_channel_allocate_handler.md">ProviderAllocateDmaChannel</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DMA_START_HANDLER callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

