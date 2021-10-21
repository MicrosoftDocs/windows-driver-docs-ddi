---
UID: NE:spbcx._SPB_REQUEST_SEQUENCE_POSITION
title: _SPB_REQUEST_SEQUENCE_POSITION (spbcx.h)
description: The SPB_REQUEST_SEQUENCE_POSITION enumeration indicates the position of an I/O request in the list of transfers for an I/O transfer sequence.
old-location: spb\spb_request_sequence_position.htm
tech.root: SPB
ms.date: 09/14/2021
keywords: ["SPB_REQUEST_SEQUENCE_POSITION enumeration"]
ms.keywords: "*PSPB_REQUEST_SEQUENCE_POSITION, SPB.spb_request_sequence_position, SPB_REQUEST_SEQUENCE_POSITION, SPB_REQUEST_SEQUENCE_POSITION enumeration [Buses], SpbRequestSequencePositionContinue, SpbRequestSequencePositionFirst, SpbRequestSequencePositionInvalid, SpbRequestSequencePositionLast, SpbRequestSequencePositionMax, SpbRequestSequencePositionSingle, _SPB_REQUEST_SEQUENCE_POSITION, spbcx/SPB_REQUEST_SEQUENCE_POSITION, spbcx/SpbRequestSequencePositionContinue, spbcx/SpbRequestSequencePositionFirst, spbcx/SpbRequestSequencePositionInvalid, spbcx/SpbRequestSequencePositionLast, spbcx/SpbRequestSequencePositionMax, spbcx/SpbRequestSequencePositionSingle"
req.header: spbcx.h
req.include-header: Spb.h
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
req.typenames: SPB_REQUEST_SEQUENCE_POSITION, *PSPB_REQUEST_SEQUENCE_POSITION
f1_keywords:
 - _SPB_REQUEST_SEQUENCE_POSITION
 - spbcx/_SPB_REQUEST_SEQUENCE_POSITION
 - PSPB_REQUEST_SEQUENCE_POSITION
 - spbcx/PSPB_REQUEST_SEQUENCE_POSITION
 - SPB_REQUEST_SEQUENCE_POSITION
 - spbcx/SPB_REQUEST_SEQUENCE_POSITION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - spbcx.h
api_name:
 - _SPB_REQUEST_SEQUENCE_POSITION
 - PSPB_REQUEST_SEQUENCE_POSITION
 - SPB_REQUEST_SEQUENCE_POSITION
---

# _SPB_REQUEST_SEQUENCE_POSITION enumeration

## -description

The **SPB_REQUEST_SEQUENCE_POSITION** enumeration indicates the position of an I/O request in the list of transfers for an [I/O transfer sequence](/windows-hardware/drivers/spb/i-o-transfer-sequences).

## -enum-fields

### -field SpbRequestSequencePositionInvalid

For internal use only.

### -field SpbRequestSequencePositionSingle

A single-transfer I/O request. This request is either a read or write ([IRP_MJ_READ](/windows-hardware/drivers/ifs/irp-mj-read) or [IRP_MJ_WRITE](/windows-hardware/drivers/kernel/irp-mj-write)) request that is not part of a sequence, or it is an [IOCTL_SPB_EXECUTE_SEQUENCE](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_execute_sequence) I/O control request for a sequence that consists of a single transfer.

The controller should select the target before performing the transfer, and release the target after the transfer finishes.

### -field SpbRequestSequencePositionFirst

The first I/O request in a sequence. This request is the read or write request that immediately follows the lock ([IOCTL_SPB_LOCK_CONTROLLER](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_lock_controller-control-code)) I/O control request that signals the start of the sequence.

The controller should select the target before performing this transfer, and the target should remain selected after the transfer finishes.

### -field SpbRequestSequencePositionContinue

An I/O request in the middle of a sequence. This request is a read or write request that is neither the first nor the last transfer in the sequence.

In some cases, the SPB framework extension (SpbCx) cannot identify the last transfer and labels the last transfer as **SpbRequestSequencePositionContinue** instead of **SpbRequestSequencePositionLast**. For more information, see the following Remarks section.

The controller should already have the target selected before it starts this transfer, and the target should remain selected after the transfer finishes.

### -field SpbRequestSequencePositionLast

The last I/O request in a sequence. This request is the read or write request that immediately precedes the unlock ([IOCTL_SPB_UNLOCK_CONTROLLER](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_unlock_controller-control-code)) I/O control request that signals the end of the sequence.

In some cases, SpbCx cannot identify the last transfer and labels the last transfer as **SpbRequestSequencePositionContinue** instead of **SpbRequestSequencePositionLast**. For more information, see the following Remarks section.

The controller should already have the target selected before it starts this transfer, and should release the target after the transfer finishes.

### -field SpbRequestSequencePositionMax

For internal use only.

## -remarks

A client (peripheral driver) of the SPB controller can perform an I/O transfer sequence by sending a series of read and write requests to a target device on the bus. Each read or write request in the series occupies a position in the list of transfers for the sequence. The values in the **SPB_REQUEST_SEQUENCE_POSITION** enumeration indicate the relative positions of the read and write requests in this list.

The [SpbRequestGetParameters](./nf-spbcx-spbrequestgetparameters.md) method retrieves the SPB-specific parameter values from an I/O request and writes them to an [SPB_REQUEST_PARAMETERS](/previous-versions/hh406209(v=vs.85)) structure. Included in these parameters is an **SPB_REQUEST_SEQUENCE_POSITION** enumeration value that indicates the position of the I/O request in the I/O transfer sequence of which it is part.

If **SpbRequestGetParameters** is called to retrieve the position value of an I/O request that is not a part of a sequence, this method assigns an appropriate **SPB_REQUEST_SEQUENCE_POSITION** enumeration value to the request.

For read and write requests, the position value is set to one of the following values: **SpbRequestSequencePositionSingle**, **SpbRequestSequencePositionFirst**, **SpbRequestSequencePositionContinue**, or **SpbRequestSequencePositionLast**.

If the client sends a simple read or write (**IRP_MJ_READ** or **IRP_MJ_WRITE**) request that is not part of a sequence, the position value is set to **SpbRequestSequencePositionSingle**.

If the client sends a lock (**IOCTL_SPB_LOCK_CONTROLLER**) request to signal the start of a sequence, the position value for the first transfer (read or write request) in the sequence is **SpbRequestSequencePositionFirst**, and the position value for the remaining transfers in the sequence is **SpbRequestSequencePositionContinue**. In this case, SpbCx cannot assign **SpbRequestSequencePositionLast** to the last transfer because it does not know that the client has sent the last read or write request until the client sends the unlock (**IOCTL_SPB_UNLOCK_CONTROLLER**) request that ends the sequence.

For lock requests, the position value is set to **SpbRequestSequencePositionFirst**. For unlock requests, the position value is set to **SpbRequestSequencePositionLast**.

Some controllers might support special operations, such as full-duplex bus transfers that simultaneously read from and write to a target device. A client can perform a custom sequence operation by locking the controller and sending a series of custom I/O requests, which SpbCx passes to the SPB controller driver's [EvtSpbControllerIoOther](./nc-spbcx-evt_spb_controller_other.md) callback function. In this case, the position value for the first custom I/O request in the sequence is **SpbRequestSequencePositionFirst**, and the position value for the remaining custom I/O requests in the sequence is **SpbRequestSequencePositionContinue**. The sequence ends when the client unlocks the controller. If the *EvtSpbControllerIoOther* callback function receives a custom I/O request that is not part of a sequence, the position value for this request is **SpbRequestSequencePositionSingle**.

For a position value of **SpbRequestSequencePositionLast**, the **Length** member of the **SPB_REQUEST_PARAMETERS** structure can be 0 to indicate that the target should simply be released and that no I/O data should be transferred (or, equivalently, to indicate that a 0-byte transfer should occur, if the controller cannot release the device without running the clock).

For position values of **SpbRequestSequencePositionContinue** and **SpbRequestSequencePositionLast**, the transfer direction might have changed from the previous transfer and the SPB controller driver might need to indicate this possible direction change on the bus (for example, an I<sup>2</sup>C controller issues a new START condition). For more information about transfer directions, see [SPB_TRANSFER_DIRECTION](../spb/ne-spb-spb_transfer_direction.md).

## -see-also

* [EvtSpbControllerIoSequence](./nc-spbcx-evt_spb_controller_sequence.md)
* [IOCTL_SPB_LOCK_CONTROLLER](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_lock_controller-control-code)
* [IOCTL_SPB_UNLOCK_CONTROLLER](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_unlock_controller-control-code)
* [IRP_MJ_READ](/windows-hardware/drivers/ifs/irp-mj-read)
* [IRP_MJ_WRITE](/windows-hardware/drivers/kernel/irp-mj-write)
* [SPB_REQUEST_PARAMETERS](/previous-versions/hh406209(v=vs.85))
* [SPB_TRANSFER_DIRECTION](../spb/ne-spb-spb_transfer_direction.md)
* [SpbRequestGetParameters](./nf-spbcx-spbrequestgetparameters.md)