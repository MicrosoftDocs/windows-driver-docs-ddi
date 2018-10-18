---
UID: NS:netdma._NET_DMA_DESCRIPTOR
title: "_NET_DMA_DESCRIPTOR"
author: windows-driver-content
description: The NET_DMA_DESCRIPTOR structure specifies the DMA transfer information for each entry in a linked list of DMA descriptors.
old-location: netvista\net_dma_descriptor.htm
tech.root: netvista
ms.assetid: 0465a8d7-1cdd-4647-9b78-557256f60c05
ms.date: 5/2/2018
ms.keywords: "*PNET_DMA_DESCRIPTOR, NET_DMA_DESCRIPTOR, NET_DMA_DESCRIPTOR structure [Network Drivers Starting with Windows Vista], NET_DMA_DESTINATION_DCA_ENABLE, NET_DMA_DESTINATION_NO_SNOOP, NET_DMA_DESTINATION_PAGE_BREAK, NET_DMA_INTERRUPT_ON_COMPLETION, NET_DMA_NULL_TRANSFER, NET_DMA_OP_TYPE_CONTEXT_CHANGE, NET_DMA_OP_TYPE_MASK, NET_DMA_RESERVED_MASK, NET_DMA_SERIALIZE_TRANSFER, NET_DMA_SOURCE_NO_SNOOP, NET_DMA_SOURCE_PAGE_BREAK, NET_DMA_STATUS_UPDATE_ON_COMPLETION, PNET_DMA_DESCRIPTOR, PNET_DMA_DESCRIPTOR structure pointer [Network Drivers Starting with Windows Vista], _NET_DMA_DESCRIPTOR, netdma/NET_DMA_DESCRIPTOR, netdma/PNET_DMA_DESCRIPTOR, netdma_ref_06e1861b-7904-4bf5-9ce5-e85ae1daa22e.xml, netvista.net_dma_descriptor"
ms.topic: struct
req.header: netdma.h
req.include-header: Netdma.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NetDMA 2.0 drivers in Windows Server 2008. (Added NextSourceAddress,   NextDestinationAddress, DCAContext32, DCAContext16, and DCAContext8 members.) Supported for NetDMA 1.1   drivers in Windows Server 2008. Supported for NetDMA 1.0 drivers in Windows Server 2008 and Windows   Vista.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	netdma.h
api_name:
-	NET_DMA_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: NET_DMA_DESCRIPTOR, *PNET_DMA_DESCRIPTOR
---

# _NET_DMA_DESCRIPTOR structure


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported in Windows 8 and later.</div><div> </div>The NET_DMA_DESCRIPTOR structure specifies the DMA transfer information for each entry in a linked
  list of DMA descriptors.


## -struct-fields




### -field TransferSize

The size, in bytes, of the memory block that is associated with this DMA descriptor. 
      

NetDMA 2.0 and later provider drivers use the 
      <b>DCAContext32</b>, 
      <b>DCAContext16</b>, and 
      <b>DCAContext8</b> members of the union with 
      <b>TransferSize</b> to support 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/network/direct-cache-access--dca-">Direct Cache Access
      (DCA)</a>.


### -field DCAContext32

A 32 bit DCA context.


### -field DCAContext32.DCAContext

A DCA context.


### -field DCAContext16

A 16 bit DCA context.


### -field DCAContext16.DCAContext

A DCA context.


### -field DCAContext16.Reserved

Reserved bits.


### -field DCAContext8

An 8 bit DCA context.


### -field DCAContext8.DCAContext

A DCA context.


### -field DCAContext8.Reserved

Reserved bits.


### -field ControlFlags

A set of flags that specify the operations that the DMA engine should perform for this DMA
     descriptor. This member must contain one or more of the following values (combined with a bitwise OR
     operation):

<table>
<tr>
<th>Unless otherwise noted, descriptions apply to when the bit is set.</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NET_DMA_SOURCE_PAGE_BREAK"></a><a id="net_dma_source_page_break"></a><dl>
<dt><b>NET_DMA_SOURCE_PAGE_BREAK</b></dt>
</dl>
</td>
<td width="60%">
A NetDMA version 2.0 or later provider starts the copy from the source physical address that is
       specified in the 
       <b>SourceAddress</b> member and when it reaches the end of the first page, it
       continues the copy from the physical address that is specified in the 
       <b>NextSourceAddress</b> member.

</td>
</tr>
<tr>
<td width="40%"><a id="NET_DMA_DESTINATION_PAGE_BREAK"></a><a id="net_dma_destination_page_break"></a><dl>
<dt><b>NET_DMA_DESTINATION_PAGE_BREAK</b></dt>
</dl>
</td>
<td width="60%">
A NetDMA version 2.0 or later provider starts the copy to the destination physical address that
       is specified in the 
       <b>DestinationAddress</b> member and when it reaches the end of the first page, it
       continues the copy to the physical address that is specified in the 
       <b>NextDestinationAddress</b> member.

</td>
</tr>
<tr>
<td width="40%"><a id="NET_DMA_OP_TYPE_CONTEXT_CHANGE"></a><a id="net_dma_op_type_context_change"></a><dl>
<dt><b>NET_DMA_OP_TYPE_CONTEXT_CHANGE</b></dt>
</dl>
</td>
<td width="60%">
The DMA engine should identify the descriptor as a 
       <i>context change</i> descriptor. 
       

The NetDMA interface submits a 
       context change descriptor to DCA-capable NetDMA providers to set the DCA target processor
       of the destination data for all of the DMA transfers on a NetDMA channel. The NetDMA interface uses
       the 
       <b>DCAContext8</b> member in a 
       context change descriptor to specify the 8-bit advanced programmable interrupt controller
       (APIC) identifier of the target processor for the channel.

A DCA-capable NetDMA provider must keep the DCA affinity of a DMA channel with a processor as long
       as it has not received a new 
       context change descriptor.

The NetDMA interface submits a 
       context change descriptor one time after the channel has been allocated and again when
       NetDMA detects that the DMA provider might have lost the hardware context (for example, after a
       suspend and resume operation).

</td>
</tr>
<tr>
<td width="40%"><a id="NET_DMA_DESTINATION_DCA_ENABLE"></a><a id="net_dma_destination_dca_enable"></a><dl>
<dt><b>NET_DMA_DESTINATION_DCA_ENABLE</b></dt>
</dl>
</td>
<td width="60%">
If the DMA operation type is a standard DMA transfer, the DMA engine should send a DCA hint for
       the destination data to the DCA target processor that has been assigned to the DMA channel. 
       

To set the DCA target processor of a DMA channel, the NetDMA interface previously submitted a 
       context change descriptor to that channel.

</td>
</tr>
<tr>
<td width="40%"><a id="NET_DMA_INTERRUPT_ON_COMPLETION"></a><a id="net_dma_interrupt_on_completion"></a><dl>
<dt><b>NET_DMA_INTERRUPT_ON_COMPLETION</b></dt>
</dl>
</td>
<td width="60%">
The DMA engine should generate an interrupt for the associated DMA channel after it processes
       this DMA descriptor.
       

When this bit is cleared, the DMA engine does not generate an interrupt.

</td>
</tr>
<tr>
<td width="40%"><a id="NET_DMA_SOURCE_NO_SNOOP"></a><a id="net_dma_source_no_snoop"></a><dl>
<dt><b>NET_DMA_SOURCE_NO_SNOOP</b></dt>
</dl>
</td>
<td width="60%">
The source address should not be snooped. 
       

When this bit is cleared, the source address is in coherent memory space, and each CPU cache line
       must be snooped. The DMA client must verify that snooping of CPU caches is not required for proper DMA
       operation.

</td>
</tr>
<tr>
<td width="40%"><a id="NET_DMA_DESTINATION_NO_SNOOP"></a><a id="net_dma_destination_no_snoop"></a><dl>
<dt><b>NET_DMA_DESTINATION_NO_SNOOP</b></dt>
</dl>
</td>
<td width="60%">
The destination address should not be snooped. 
       

When this bit is cleared, the destination address is in coherent memory space, and each CPU cache
       line must be snooped. The DMA client must verify that snooping of CPU caches is not required for
       proper DMA operation.

</td>
</tr>
<tr>
<td width="40%"><a id="NET_DMA_STATUS_UPDATE_ON_COMPLETION"></a><a id="net_dma_status_update_on_completion"></a><dl>
<dt><b>NET_DMA_STATUS_UPDATE_ON_COMPLETION</b></dt>
</dl>
</td>
<td width="60%">
The 
       <b>CompletionVirtualAddress</b> and 
       <b>CompletionPhysicalAddress</b> members in the 
       <a href="https://msdn.microsoft.com/0d09a9e9-06c5-4026-9053-ac74a59509cc">
       NET_DMA_CHANNEL_PARAMETERS</a> structure reference a completion status value. The DMA engine updates
       the completion status value when it completes the processing of this descriptor. 
       

The completion status value is a 64-bit-wide combination of the physical address of the most recent
       DMA descriptor that the DMA engine processed, and additional status information.

When this bit is cleared, the DMA engine does not use 
       <b>CompletionVirtualAddress</b> or 
       <b>CompletionPhysicalAddress</b>.

</td>
</tr>
<tr>
<td width="40%"><a id="NET_DMA_SERIALIZE_TRANSFER"></a><a id="net_dma_serialize_transfer"></a><dl>
<dt><b>NET_DMA_SERIALIZE_TRANSFER</b></dt>
</dl>
</td>
<td width="60%">
The DMA engine guarantees that all writes for this descriptor, including data and completion
       status, are complete before it reads the data for the next descriptor. 
       

When this bit is cleared, the DMA engine can start processing the next descriptor before it
       completes the processing of this descriptor.

</td>
</tr>
<tr>
<td width="40%"><a id="NET_DMA_NULL_TRANSFER"></a><a id="net_dma_null_transfer"></a><dl>
<dt><b>NET_DMA_NULL_TRANSFER</b></dt>
</dl>
</td>
<td width="60%">
A DMA transfer is not required for this descriptor. The DMA engine is not required to check the 
       <b>TransferSize</b>, 
       <b>SourceAddress</b>, or 
       <b>DestinationAddress</b> members. 
       

When this bit is cleared, a DMA transfer might be required or it might be a zero-length transfer.
       The DMA engine must check the 
       <b>TransferSize</b>, 
       <b>SourceAddress</b>, or 
       <b>DestinationAddress</b> members.

<div class="alert"><b>Note</b>  If this bit is set or cleared, the NetDMA client must always ensure that the descriptor defines
       valid transfer parameters.</div>
<div> </div>
</td>
</tr>
</table>
 

The following bitmasks identify the remaining bits in the 
      <b>ControlFlags</b> member:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NET_DMA_OP_TYPE_MASK"></a><a id="net_dma_op_type_mask"></a><dl>
<dt><b>NET_DMA_OP_TYPE_MASK</b></dt>
</dl>
</td>
<td width="60%">
A bit mask that specifies bits that are reserved for a DMA operation type. The NetDMA interface
       sets these bits to zero.

</td>
</tr>
<tr>
<td width="40%"><a id="NET_DMA_RESERVED_MASK"></a><a id="net_dma_reserved_mask"></a><dl>
<dt><b>NET_DMA_RESERVED_MASK</b></dt>
</dl>
</td>
<td width="60%">
A bit mask that specifies bits that are reserved for future applications. The NetDMA interface
       sets these bits to zero.

</td>
</tr>
</table>
 


### -field SourceAddress

The physical address of a memory block that is a source for the DMA transfer.


### -field DestinationAddress

The physical address of a memory block that is a destination for the DMA transfer.


### -field NextDescriptor

The physical address of the next NET_DMA_DESCRIPTOR structure in the linked list of descriptors.
     If this descriptor is the last descriptor in the list, 
     <b>NextDescriptor</b> is <b>NULL</b>.


### -field Reserved1

A ULONG64 value that is reserved for the DMA engine or the DMA provider driver to use. NetDMA 2.0
      and later provider drivers use the 
      <b>NextSourceAddress</b> member of the union with 
      <b>Reserved1</b> to support 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/network/source-and-destination-page-break">Source and Destination Page
      Break</a>.


### -field NextSourceAddress

The physical address of the second page of source address that is used in source page
      break.


### -field Reserved2

A ULONG64 value that is reserved for use the DMA engine or the DMA provider driver to use. NetDMA
      2.0 and later provider drivers use the 
      <b>NextDestinationAddress</b> member of the union with 
      <b>Reserved2</b> to support 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/network/source-and-destination-page-break">Source and Destination Page
      Break</a>.


### -field NextDestinationAddress

The physical address of the second page of destination address that is used in destination page
      break.


### -field UserContext1

A ULONG64 value that is reserved for the NetDMA interface to use.


### -field UserContext2

A ULONG64 value that is reserved for the NetDMA interface to use.


## -remarks



The NET_DMA_DESCRIPTOR structure specifies the source, destination, and control information for a
    single DMA transfer in a linked list of DMA descriptors.

To start a DMA transfer, the NetDMA interface supplies the physical address of a NET_DMA_DESCRIPTOR
    structure at the 
    <i>DescriptorPhysicalAddress</i> parameter of the DMA provider driver's 
    <a href="https://msdn.microsoft.com/0926e8c4-f2ca-401f-abe8-76aec359a1e2">ProviderStartDma</a> function. The 
    <i>DescriptorVirtualAddress</i> parameter contains the virtual address of the descriptor.

The 
    <b>NextDescriptor</b> member of a NET_DMA_DESCRIPTOR structure contains the physical address of the next
    NET_DMA_DESCRIPTOR structure in the linked list of descriptors.

The NetDMA interface calls a DMA provider driver's 
    <a href="https://msdn.microsoft.com/51de8ddf-cbfc-4e49-b44a-207307a937e7">ProviderAppendDma</a> function to append a
    linked list of DMA descriptors after the last descriptor on a DMA channel.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568732">NET_DMA_CHANNEL_PARAMETERS</a>



<a href="https://msdn.microsoft.com/51de8ddf-cbfc-4e49-b44a-207307a937e7">ProviderAppendDma</a>



<a href="https://msdn.microsoft.com/0926e8c4-f2ca-401f-abe8-76aec359a1e2">ProviderStartDma</a>
 

 

