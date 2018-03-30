---
UID: NC:netdma.DMA_APPEND_HANDLER
title: DMA_APPEND_HANDLER
author: windows-driver-content
description: The ProviderAppendDma function appends a linked list of DMA descriptors to the last descriptor on a DMA channel.
old-location: netvista\providerappenddma.htm
old-project: netvista
ms.assetid: 51de8ddf-cbfc-4e49-b44a-207307a937e7
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: DMA_APPEND_HANDLER, ProviderAppendDma, ProviderAppendDma callback function [Network Drivers Starting with Windows Vista], netdma/ProviderAppendDma, netdma_ref_ce5895a2-ac0c-4b98-98be-9f95edf091d3.xml, netvista.providerappenddma
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	netdma.h
api_name:
-	ProviderAppendDma
product: Windows
targetos: Windows
req.typenames: MIRACAST_DRIVER_INTERFACE, *PMIRACAST_DRIVER_INTERFACE
---

# DMA_APPEND_HANDLER callback


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported 

in Windows 8 and later.</div><div> </div>The 
  <i>ProviderAppendDma</i> function appends a linked list of DMA descriptors to the last descriptor on a DMA
  channel.


## -parameters




### -param ProviderChannelContext [in]

A pointer that identifies a DMA channel's context area. The DMA provider returned this handle to
     NetDMA at the location that is specified in the 
     <i>pProviderChannelContext</i> parameter of the 
     <a href="https://msdn.microsoft.com/42bc0e08-3d85-424f-aaa4-4df788d3706a">
     ProviderAllocateDmaChannel</a> function.


### -param DescriptorVirtualAddress [in]

A pointer to the virtual address of the first 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568734">NET_DMA_DESCRIPTOR</a> structure in a linked
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



<i>ProviderAppendDma</i> returns one of the following status values:

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
    <i>ProviderAppendDma</i> function to append a linked list of DMA descriptors after the last descriptor on
    a DMA channel. The NetDMA interface can call 
    <i>ProviderAppendDma</i> any number of times after a DMA transfer is started. However, the NetDMA
    interface must call the 
    <a href="https://msdn.microsoft.com/0926e8c4-f2ca-401f-abe8-76aec359a1e2">ProviderStartDma</a> function after a channel
    reset or abort, or after the DMA channel is first allocated.

<div class="alert"><b>Note</b>  In NetDMA 2.0 and later versions, the linked list of descriptors is not
    NULL-terminated. The 
    <b>NextDescriptor</b> member in the last descriptor in the linked list specifies the physical address of
    the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568734">NET_DMA_DESCRIPTOR</a> structure that will be
    used in the subsequent call to the 
    <b>ProviderAppendDma</b> function. A NetDMA 2.0
    provider driver can cache the address in 
    <b>NextDescriptor</b> and use this address as the beginning of the linked list for the next Append
    operation.</div>
<div> </div>
The NetDMA interface sets the 
    <b>NextDescriptor</b> member of the last descriptor to the beginning of the new chain of descriptors
    before calling 
    <i>ProviderAppendDma</i>.

If the current descriptor in an active transfer is the last descriptor, the DMA engine must reread the
    last descriptor. The 
    <b>NextDescriptor</b> member in the last 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568734">NET_DMA_DESCRIPTOR</a> structure should have
    a new address, and the DMA engine should continue with the next descriptor. If the current descriptor is
    not the last descriptor, the DMA engine can continue processing DMA descriptors with no additional
    tasks.

NetDMA calls 
    <i>ProviderAppendDma</i> at IRQL &lt;= DISPATCH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568734">NET_DMA_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/42bc0e08-3d85-424f-aaa4-4df788d3706a">ProviderAllocateDmaChannel</a>



<a href="https://msdn.microsoft.com/0926e8c4-f2ca-401f-abe8-76aec359a1e2">ProviderStartDma</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DMA_APPEND_HANDLER callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
