---
UID: NF:storport.StorPortGetPhysicalAddress
title: StorPortGetPhysicalAddress function (storport.h)
description: The StorPortGetPhysicalAddress routine converts a given virtual address range to a physical address range for a DMA operation.
old-location: storage\storportgetphysicaladdress.htm
tech.root: storage
ms.assetid: 2b39a6e4-2e11-4b4e-9218-92336629ae80
ms.date: 03/29/2018
keywords: ["StorPortGetPhysicalAddress function"]
ms.keywords: StorPortGetPhysicalAddress, StorPortGetPhysicalAddress routine [Storage Devices], storage.storportgetphysicaladdress, storport/StorPortGetPhysicalAddress, storprt_fea6d754-844c-4ee9-8153-97f2f0e9ee80.xml
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: Storport.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortGetPhysicalAddress
 - storport/StorPortGetPhysicalAddress
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Storport.lib
 - Storport.dll
api_name:
 - StorPortGetPhysicalAddress
---

# StorPortGetPhysicalAddress function


## -description

The <b>StorPortGetPhysicalAddress</b> routine converts a given virtual address range to a physical address range for a DMA operation.

## -parameters

### -param HwDeviceExtension 

[in]
A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver in the <b>DeviceExtension->HwDeviceExtension</b> member of the device object for the HBA immediately after the miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinitialize">StorPortInitialize</a>. The port driver frees this memory when it removes the device.

### -param Srb 

[in, optional]
Pointer to the SCSI request block if the virtual address to be converted comes from that SRB's <b>DataBuffer</b> member or <b>SenseInfoBuffer</b> member. Otherwise, this parameter must be <b>NULL</b>.

### -param VirtualAddress 

[in]
Pointer to the base virtual address to be converted. If this virtual address falls within the range for an SRB-supplied <b>DataBuffer</b>, the caller also must provide the <i>Srb</i> pointer.

### -param Length 

[out]
Pointer to a value indicating the number of bytes mapped, starting at the returned physical address.

## -returns

<b>StorPortGetPhysicalAddress</b> returns the corresponding physical address for a given virtual address. If the given address cannot be converted, the function returns <b>NULL</b>.

## -remarks

If the virtual address passed to <b>StorPortGetPhysicalAddress</b> is obtained from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportallocatecontiguousmemoryspecifycachenode">StorPortAllocateContiguousMemorySpecifyCacheNode</a>, the value returned for <i>Length</i> should be ignored.

Starting in Windows 8, the <i>Srb</i> parameter may point to either <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_storage_request_block">STORAGE_REQUEST_BLOCK</a>. If the function identifier in the <b>Function</b> field of <i>Srb</i> is <b>SRB_FUNCTION_STORAGE_REQUEST_BLOCK</b>, the SRB is a <b>STORAGE_REQUEST_BLOCK</b> request structure.

<b>StorPortGetPhysicalAddress</b> uses <b>STOR_PHYSICAL_ADDRESS</b> to represent physical addresses.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>typedef PHYSICAL_ADDRESS STOR_PHYSICAL_ADDRESS, *PSTOR_PHYSICAL_ADDRESS;
</pre>
</td>
</tr>
</table></span></div>
The <b>STOR_PHYSICAL_ADDRESS</b> type is an operating system-independent data type that Storport miniport drivers use to represent either a physical addresses or a bus-relative address.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_storage_request_block">STORAGE_REQUEST_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetphysicaladdress">ScsiPortGetPhysicalAddress</a>

