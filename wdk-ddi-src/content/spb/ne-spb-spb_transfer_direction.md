---
UID: NE:spb.SPB_TRANSFER_DIRECTION
title: SPB_TRANSFER_DIRECTION (spb.h)
description: The SPB_TRANSFER_DIRECTION enumeration describes the direction (read or write) of a single transfer in an I/O transfer sequence.
old-location: spb\spb_transfer_direction.htm
tech.root: SPB
ms.date: 11/15/2021
keywords: ["SPB_TRANSFER_DIRECTION enumeration"]
ms.keywords: "*PSPB_TRANSFER_DIRECTION, SPB.spb_transfer_direction, SPB_TRANSFER_DIRECTION, SPB_TRANSFER_DIRECTION enumeration [Buses], SpbTransferDirectionFromDevice, SpbTransferDirectionMax, SpbTransferDirectionNone, SpbTransferDirectionToDevice, spb/SPB_TRANSFER_DIRECTION, spb/SpbTransferDirectionFromDevice, spb/SpbTransferDirectionMax, spb/SpbTransferDirectionNone, spb/SpbTransferDirectionToDevice"
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
req.typenames: SPB_TRANSFER_DIRECTION, *PSPB_TRANSFER_DIRECTION
f1_keywords:
 - SPB_TRANSFER_DIRECTION
 - spb/SPB_TRANSFER_DIRECTION
 - PSPB_TRANSFER_DIRECTION
 - spb/PSPB_TRANSFER_DIRECTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Spb.h
api_name:
 - SPB_TRANSFER_DIRECTION
 - PSPB_TRANSFER_DIRECTION
---

# SPB_TRANSFER_DIRECTION enumeration

## -description

The **SPB_TRANSFER_DIRECTION** enumeration describes the direction (read or write) of a single transfer in an [I/O transfer sequence](/windows-hardware/drivers/spb/i-o-transfer-sequences).

## -enum-fields

### -field SpbTransferDirectionNone

The data transfer direction is undefined.

### -field SpbTransferDirectionFromDevice

The data transfer direction is from the device to system memory (read from device).

### -field SpbTransferDirectionToDevice

The data transfer direction is from system memory to the device (write to device).

### -field SpbTransferDirectionMax

Reserved for use by the operating system.

## -remarks

The values in this enumeration indicate the directions of the individual transfers in an I/O transfer sequence. The input buffer for an [IOCTL_SPB_EXECUTE_SEQUENCE](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_execute_sequence) I/O control request is an [SPB_TRANSFER_LIST](./ns-spb-spb_transfer_list.md) structure that specifies a list of transfers for the sequence. Each transfer is described by an [SPB_TRANSFER_LIST_ENTRY](./ns-spb-spb_transfer_list_entry.md) structure that contains the transfer parameters, which include the transfer direction. The transfer direction is **SpbTransferDirectionFromDevice** for a read operation, and is **SpbTransferDirectionToDevice** for a write operation.

Your SPB controller driver can call  the [SpbRequestGetParameters](../spbcx/nf-spbcx-spbrequestgetparameters.md) method to retrieve a set of SPB-specific parameters from an I/O request. One of these parameters is an **SPB_TRANSFER_DIRECTION** enumeration value that indicates the transfer direction of the previous I/O request. The SPB controller driver can use this direction value to determine whether the current read or write ([IRP_MJ_READ](/windows-hardware/drivers/ifs/irp-mj-read) or [IRP_MJ_WRITE](/windows-hardware/drivers/kernel/irp-mj-write)) request requires a change in transfer direction on the bus.

In addition, **SpbRequestGetParameters** retrieves a position value that indicates the relative position of a read or write  request in the list of transfers for the multiple-request sequence. If a read request or a write request has a position value of **SpbRequestSequencePositionSingle** or **SpbRequestSequencePositionFirst**, the direction value for the previous transfer is **SpbTransferDirectionNone** (that is, there is no previous transfer direction). For a read or write request that has a position value of **SpbRequestSequencePositionMiddle** or **SpbRequestSequencePositionLast**, the direction value indicates whether the previous transfer was a read or a write. For an unlock ([IOCTL_SPB_UNLOCK_CONTROLLER](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_unlock_controller-control-code)) request, which has a position value of **SpbRequestSequencePositionLast**, the direction value indicates whether the last transfer in the sequence was a read or a write.

A lock ([IOCTL_SPB_LOCK_CONTROLLER](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_lock_controller-control-code)) request has no previous direction. Similarly, an I/O control request that is passed to the [EvtSpbControllerIoOther](../spbcx/nc-spbcx-evt_spb_controller_other.md) callback function has no previous direction. For either of these requests, the previous direction value retrieved by **SpbRequestGetParameters** is **SpbTransferDirectionNone**.

## -see-also

- [EvtSpbControllerIoOther](../spbcx/nc-spbcx-evt_spb_controller_other.md)
- [IOCTL_SPB_EXECUTE_SEQUENCE](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_execute_sequence)
- [IOCTL_SPB_LOCK_CONTROLLER](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_lock_controller-control-code)
- [IOCTL_SPB_UNLOCK_CONTROLLER](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_unlock_controller-control-code)
- [IRP_MJ_READ](/windows-hardware/drivers/ifs/irp-mj-read)
- [IRP_MJ_WRITE](/windows-hardware/drivers/kernel/irp-mj-write)
- [SPB_TRANSFER_LIST](./ns-spb-spb_transfer_list.md)
- [SPB_TRANSFER_LIST_ENTRY](./ns-spb-spb_transfer_list_entry.md)
- [SpbRequestGetParameters](../spbcx/nf-spbcx-spbrequestgetparameters.md)
