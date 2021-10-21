---
UID: NS:spb.SPB_TRANSFER_LIST_ENTRY
title: SPB_TRANSFER_LIST_ENTRY (spb.h)
description: The SPB_TRANSFER_LIST_ENTRY structure describes a single transfer in an I/O transfer sequence.
old-location: spb\spb_transfer_list_entry.htm
tech.root: SPB
ms.date: 09/14/2021
keywords: ["SPB_TRANSFER_LIST_ENTRY structure"]
ms.keywords: "*PSPB_TRANSFER_LIST_ENTRY, PSPB_TRANSFER_LIST_ENTRY, PSPB_TRANSFER_LIST_ENTRY structure pointer [Buses], SPB.spb_transfer_list_entry, SPB_TRANSFER_LIST_ENTRY, SPB_TRANSFER_LIST_ENTRY structure [Buses], spb/PSPB_TRANSFER_LIST_ENTRY, spb/SPB_TRANSFER_LIST_ENTRY"
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
req.typenames: SPB_TRANSFER_LIST_ENTRY, *PSPB_TRANSFER_LIST_ENTRY
f1_keywords:
 - SPB_TRANSFER_LIST_ENTRY
 - spb/SPB_TRANSFER_LIST_ENTRY
 - PSPB_TRANSFER_LIST_ENTRY
 - spb/PSPB_TRANSFER_LIST_ENTRY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Spb.h
api_name:
 - SPB_TRANSFER_LIST_ENTRY
 - PSPB_TRANSFER_LIST_ENTRY
---

# SPB_TRANSFER_LIST_ENTRY structure

## -description

The **SPB_TRANSFER_LIST_ENTRY** structure describes a single transfer in an [I/O transfer sequence](/windows-hardware/drivers/spb/i-o-transfer-sequences).

## -struct-fields

### -field Direction

The direction of the transfer. This member is set to one of the following [SPB_TRANSFER_DIRECTION](/windows-hardware/drivers/ddi/spb/ne-spb-spb_transfer_direction) enumeration values:

* **SpbTransferDirectionFromDevice**
* **SpbTransferDirectionToDevice**

### -field DelayInUs

An optional delay, in microseconds, before this transfer begins. For more information, see the description of the **DelayInUs** member in [SPB_TRANSFER_DESCRIPTOR](/windows-hardware/drivers/ddi/spbcx/ns-spbcx-spb_transfer_descriptor).

### -field Buffer

The buffer for this transfer. This member uses one of the following buffer formats: simple buffer, scatter-gather list, or (for kernel-mode clients) MDL. For more information about buffer formats, see [SPB_TRANSFER_BUFFER](/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_buffer).

## -remarks

To request an I/O transfer sequence for a target device on the bus, a client (peripheral driver) of the SPB controller driver sends an [IOCTL_SPB_EXECUTE_SEQUENCE](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_execute_sequence) request that describes the sequence. The transfers in the sequence are described by an [SPB_TRANSFER_LIST](/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_list) structure that is followed by an array of one or more **SPB_TRANSFER_LIST_ENTRY** structures. Each element in this array describes an individual transfer in the sequence.

## -see-also

* [IOCTL_SPB_EXECUTE_SEQUENCE](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_execute_sequence)
* [SPB_TRANSFER_BUFFER](/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_buffer)
* [SPB_TRANSFER_DESCRIPTOR](/windows-hardware/drivers/ddi/spbcx/ns-spbcx-spb_transfer_descriptor)
* [SPB_TRANSFER_DIRECTION](/windows-hardware/drivers/ddi/spb/ne-spb-spb_transfer_direction)
* [SPB_TRANSFER_LIST](/windows-hardware/drivers/ddi/spb/ns-spb-spb_transfer_list)
