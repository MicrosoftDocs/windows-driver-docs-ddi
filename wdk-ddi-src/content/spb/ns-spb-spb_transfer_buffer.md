---
UID: NS:spb.SPB_TRANSFER_BUFFER
title: SPB_TRANSFER_BUFFER (spb.h)
description: The SPB_TRANSFER_BUFFER structure describes the data buffer for an individual transfer in an I/O transfer sequence.
old-location: spb\spb_transfer_buffer.htm
tech.root: SPB
ms.date: 11/15/2021
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

The **SPB_TRANSFER_BUFFER** structure describes the data buffer for an individual transfer in an [I/O transfer sequence](/windows-hardware/drivers/spb/i-o-transfer-sequences).

## -struct-fields

### -field Format

The buffer format. This member is set to one of the following [SPB_TRANSFER_BUFFER_FORMAT](./ne-spb-spb_transfer_buffer_format.md) enumeration values:

- **SpbTransferBufferFormatSimple**
- **SpbTransferBufferFormatList**
- **SpbTransferBufferFormatSimpleNonPaged**
- **SpbTransferBufferFormatMdl**

**SpbTransferBufferFormatMdl** is a valid value only for I/O transfer sequences that are requested by clients of the SPB controller driver that are kernel-mode components.

### -field Simple

A SPB_TRANSFER_BUFFER_LIST_ENTRY structure that specifies the base address and the length of a simple transfer buffer. Use this member of the union if **Format** is **SpbTransferBufferFormatSimple** or **SpbTransferBufferFormatSimpleNonPaged**. The **SpbTransferBufferFormatSimpleNonPaged** format is used only by kernel-mode clients.

### -field BufferList

A scatter-gather list that consists of an array of buffer descriptors. Use this member of the union if **Format** is **SpbTransferBufferFormatList**.

### -field BufferList.List

A pointer to an array of **SPB_TRANSFER_BUFFER_LIST_ENTRY** structures that describe the buffers in the scatter-gather list.

### -field BufferList.ListCe

The number of elements in the **List** array.

### -field Mdl

A pointer to an MDL that describes the buffer. This member is used only by kernel-mode clients. Use this member of the union if **Format** is **SpbTransferBufferFormatMdl**. For more information, see Remarks.

## -remarks

This structure is used by an [SPB_TRANSFER_LIST_ENTRY](./ns-spb-spb_transfer_list_entry.md) structure to describe a transfer buffer.

The **Mdl** member of this structure can be used only by clients of the SPB controller driver that are kernel-mode components. User-mode clients must not use this member. For more information about MDLs, see [Using MDLs](/windows-hardware/drivers/kernel/using-mdls).

## -see-also

- [SPB_TRANSFER_BUFFER_FORMAT](./ne-spb-spb_transfer_buffer_format.md)
- [SPB_TRANSFER_BUFFER_LIST_ENTRY](./ns-spb-spb_transfer_buffer_list_entry.md)
- [SPB_TRANSFER_LIST_ENTRY](./ns-spb-spb_transfer_list_entry.md)
