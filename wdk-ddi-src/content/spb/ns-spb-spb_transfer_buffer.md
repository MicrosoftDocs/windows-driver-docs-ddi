---
UID: NS:spb.SPB_TRANSFER_BUFFER
title: SPB_TRANSFER_BUFFER (spb.h)
description: The SPB_TRANSFER_BUFFER structure describes the data buffer for an individual transfer in an I/O transfer sequence.
old-location: spb\spb_transfer_buffer.htm
tech.root: SPB
ms.date: 04/30/2018
keywords: ["SPB_TRANSFER_BUFFER structure"]
ms.keywords: "*PSPB_TRANSFER_BUFFER, PSPB_TRANSFER_BUFFER, PSPB_TRANSFER_BUFFER structure pointer [Buses], SPB.spb_transfer_buffer, SPB_TRANSFER_BUFFER, SPB_TRANSFER_BUFFER structure [Buses], spb/PSPB_TRANSFER_BUFFER, spb/SPB_TRANSFER_BUFFER"
req.header: spb.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
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
targetos: Windows
req.typenames: SPB_TRANSFER_BUFFER, *PSPB_TRANSFER_BUFFER
f1_keywords:
 - SPB_TRANSFER_BUFFER
 - spb/SPB_TRANSFER_BUFFER
 - PSPB_TRANSFER_BUFFER
 - spb/PSPB_TRANSFER_BUFFER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Spb.h
api_name:
 - SPB_TRANSFER_BUFFER
 - PSPB_TRANSFER_BUFFER
---

# SPB_TRANSFER_BUFFER structure


## -description

The <b>SPB_TRANSFER_BUFFER</b> structure describes the data buffer for an individual transfer in an <a href="/windows-hardware/drivers/spb/i-o-transfer-sequences">I/O transfer sequence</a>.

## -struct-fields

### -field Format

The buffer format.  This member is set to one of the following <a href="/windows-hardware/drivers/ddi/spb/ne-spb-spb_transfer_buffer_format">SPB_TRANSFER_BUFFER_FORMAT</a> enumeration values:

<ul>
<li><b>SpbTransferBufferFormatSimple</b></li>
<li><b>SpbTransferBufferFormatList</b></li>
<li><b>SpbTransferBufferFormatSimpleNonPaged</b></li>
<li><b>SpbTransferBufferFormatMdl</b></li>
</ul>
<b>SpbTransferBufferFormatMdl</b> is a valid value only for I/O transfer sequences that are requested by clients of the SPB controller driver that are kernel-mode components.

### -field Simple

A SPB_TRANSFER_BUFFER_LIST_ENTRY  structure that specifies the base address and the length of a simple transfer buffer. Use this member of the union if <b>Format</b> is <b>SpbTransferBufferFormatSimple</b> or <b>SpbTransferBufferFormatSimpleNonPaged</b>. The <b>SpbTransferBufferFormatSimpleNonPaged</b> format is used only by kernel-mode clients.

### -field BufferList

A scatter-gather list that consists of an array of buffer descriptors. Use this member of the union if <b>Format</b> is <b>SpbTransferBufferFormatList</b>.

### -field BufferList.List

A pointer to an array of <b>SPB_TRANSFER_BUFFER_LIST_ENTRY</b> structures that describe the buffers in the scatter-gather list.

### -field BufferList.ListCe

The number of elements in the <b>List</b> array.

### -field Mdl

A pointer to an MDL that describes the buffer. This member is used only by kernel-mode clients. Use this member of the union if <b>Format</b> is <b>SpbTransferBufferFormatMdl</b>. For more information, see Remarks.

## -remarks

This structure is used by an <a href="/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_list_entry">SPB_TRANSFER_LIST_ENTRY</a> structure to describe a transfer buffer.

The <b>Mdl</b> member of this structure can be used only by clients of the SPB controller driver that are kernel-mode components. User-mode clients must not use this member. For more information about MDLs, see <a href="/windows-hardware/drivers/kernel/using-mdls">Using MDLs</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/spb/ne-spb-spb_transfer_buffer_format">SPB_TRANSFER_BUFFER_FORMAT</a>



<a href="/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_buffer_list_entry">SPB_TRANSFER_BUFFER_LIST_ENTRY</a>



<a href="/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_list_entry">SPB_TRANSFER_LIST_ENTRY</a>

