---
UID: NS:spb.SPB_TRANSFER_BUFFER_LIST_ENTRY
title: SPB_TRANSFER_BUFFER_LIST_ENTRY (spb.h)
description: The SPB_TRANSFER_BUFFER_LIST_ENTRY structure describes either a simple transfer buffer, or an element in an array of one or more transfer buffers.
old-location: spb\spb_transfer_buffer_list_entry.htm
tech.root: SPB
ms.date: 09/13/2021
keywords: ["SPB_TRANSFER_BUFFER_LIST_ENTRY structure"]
ms.keywords: "*PSPB_TRANSFER_BUFFER_LIST_ENTRY, PSPB_TRANSFER_BUFFER_LIST_ENTRY, PSPB_TRANSFER_BUFFER_LIST_ENTRY structure pointer [Buses], SPB.spb_transfer_buffer_list_entry, SPB_TRANSFER_BUFFER_LIST_ENTRY, SPB_TRANSFER_BUFFER_LIST_ENTRY structure [Buses], spb/PSPB_TRANSFER_BUFFER_LIST_ENTRY, spb/SPB_TRANSFER_BUFFER_LIST_ENTRY"
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
req.typenames: SPB_TRANSFER_BUFFER_LIST_ENTRY, *PSPB_TRANSFER_BUFFER_LIST_ENTRY
f1_keywords:
 - SPB_TRANSFER_BUFFER_LIST_ENTRY
 - spb/SPB_TRANSFER_BUFFER_LIST_ENTRY
 - PSPB_TRANSFER_BUFFER_LIST_ENTRY
 - spb/PSPB_TRANSFER_BUFFER_LIST_ENTRY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Spb.h
api_name:
 - SPB_TRANSFER_BUFFER_LIST_ENTRY
 - PSPB_TRANSFER_BUFFER_LIST_ENTRY
---

# SPB_TRANSFER_BUFFER_LIST_ENTRY structure

## -description

The **SPB_TRANSFER_BUFFER_LIST_ENTRY** structure describes either a simple transfer buffer, or an element in an array of one or more transfer buffers.

## -struct-fields

### -field Buffer

The virtual address of the transfer buffer. For a transfer that is requested by a client of the SPB controller driver that runs in user mode, this buffer must reside entirely in user-mode memory.

### -field BufferCb

The size, in bytes, of the transfer buffer that *Buffer* points to.

## -remarks

To request an [I/O transfer sequence](/windows-hardware/drivers/spb/i-o-transfer-sequences) for a target device on the bus, a client (peripheral driver) of the SPB controller driver sends an [IOCTL_SPB_EXECUTE_SEQUENCE](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_execute_sequence) request that describes the sequence. The transfers in the sequence are described by an [SPB_TRANSFER_LIST](/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_list) structure that is followed by an array of one or more [SPB_TRANSFER_LIST_ENTRY](/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_list_entry) structures. Each element in this array describes an individual transfer in the sequence, and each element contains an [SPB_TRANSFER_BUFFER](/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_buffer) structure that describes the buffer to use for the transfer.

If the buffer format is **SpbTransferBufferFormatSimple**, an **SPB_TRANSFER_BUFFER** structure contains a single **SPB_TRANSFER_BUFFER_LIST_ENTRY** structure that describes a simple buffer that is specified by an address and a length. If the buffer format is **SpbTransferBufferFormatList**, the buffer is a scatter-gather list, and the **SPB_TRANSFER_BUFFER** structure contains a pointer to an **SPB_TRANSFER_BUFFER_LIST_ENTRY** array that describes the list.

## -see-also

* [IOCTL_SPB_EXECUTE_SEQUENCE](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_execute_sequence)
* [SPB_TRANSFER_BUFFER](/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_buffer)
* [SPB_TRANSFER_LIST](/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_list)
* [SPB_TRANSFER_LIST_ENTRY](/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_list_entry)
