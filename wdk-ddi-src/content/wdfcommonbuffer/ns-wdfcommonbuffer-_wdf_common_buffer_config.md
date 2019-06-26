---
UID: NS:wdfcommonbuffer._WDF_COMMON_BUFFER_CONFIG
title: _WDF_COMMON_BUFFER_CONFIG (wdfcommonbuffer.h)
description: The WDF_COMMON_BUFFER_CONFIG structure contains configuration information for a common buffer.
old-location: wdf\wdf_common_buffer_config.htm
tech.root: wdf
ms.assetid: 19e98448-6951-4eb4-bca1-8119cd6f7713
ms.date: 02/26/2018
ms.keywords: "*PWDF_COMMON_BUFFER_CONFIG, DFCommonBufferObjectRef_6b9d3f2e-8954-4777-b5e4-9828f73feec3.xml, PWDF_COMMON_BUFFER_CONFIG, PWDF_COMMON_BUFFER_CONFIG structure pointer, WDF_COMMON_BUFFER_CONFIG, WDF_COMMON_BUFFER_CONFIG structure, _WDF_COMMON_BUFFER_CONFIG, kmdf.wdf_common_buffer_config, wdf.wdf_common_buffer_config, wdfcommonbuffer/PWDF_COMMON_BUFFER_CONFIG, wdfcommonbuffer/WDF_COMMON_BUFFER_CONFIG"
ms.topic: struct
req.header: wdfcommonbuffer.h
req.include-header: WdfCommonBuffer.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
- wdfcommonbuffer.h
api_name:
- WDF_COMMON_BUFFER_CONFIG
product:
- Windows
targetos: Windows
req.typenames: WDF_COMMON_BUFFER_CONFIG, *PWDF_COMMON_BUFFER_CONFIG
---

# _WDF_COMMON_BUFFER_CONFIG structure


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_COMMON_BUFFER_CONFIG</b> structure contains configuration information for a common buffer.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field AlignmentRequirement

The alignment requirement for a common buffer. This value must be one less than the alignment boundary. For example, you can specify 15 for a 16-byte alignment boundary and 31 for a 32-byte alignment boundary. You can also use one of the FILE_<i>Xxxx</i>_ALIGNMENT constants that are defined in <i>Wdm.h</i>.   


## -remarks



The <b>WDF_COMMON_BUFFER_CONFIG</b> structure is used as input to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfcommonbuffer/nf-wdfcommonbuffer-wdfcommonbuffercreatewithconfig">WdfCommonBufferCreateWithConfig</a> method.

If your driver specifies an alignment requirement that is greater that the computer's page size (PAGE_SIZE), the logical addresses that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfcommonbuffer/nf-wdfcommonbuffer-wdfcommonbuffergetalignedlogicaladdress">WdfCommonBufferGetAlignedLogicalAddress</a> method returns are always aligned to the specified alignment requirement, but the virtual addresses that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfcommonbuffer/nf-wdfcommonbuffer-wdfcommonbuffergetalignedvirtualaddress">WdfCommonBufferGetAlignedVirtualAddress</a> method returns might not be aligned to the alignment requirement.

If your driver specifies an alignment requirement that is less than the computer's page size, all logical and virtual addresses are aligned to the specified alignment requirement.

For more information about specifying alignment requirements, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/enabling-dma-transactions">Enabling DMA Transactions</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-common-buffers">Using Common Buffers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfcommonbuffer/nf-wdfcommonbuffer-wdfcommonbuffercreatewithconfig">WdfCommonBufferCreateWithConfig</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfcommonbuffer/nf-wdfcommonbuffer-wdfcommonbuffergetalignedlogicaladdress">WdfCommonBufferGetAlignedLogicalAddress</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfcommonbuffer/nf-wdfcommonbuffer-wdfcommonbuffergetalignedvirtualaddress">WdfCommonBufferGetAlignedVirtualAddress</a>
 

 

