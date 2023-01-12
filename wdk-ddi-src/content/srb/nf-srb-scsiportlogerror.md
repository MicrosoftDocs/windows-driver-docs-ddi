---
UID: NF:srb.ScsiPortLogError
title: ScsiPortLogError function (srb.h)
description: The ScsiPortLogError routine logs errors to the system event log when a miniport driver or its HBA detects a SCSI error condition.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportlogerror.htm
tech.root: storage
ms.date: 08/31/2022
keywords: ["ScsiPortLogError function"]
ms.keywords: ScsiPortLogError, ScsiPortLogError routine [Storage Devices], scsiprt_5d3ec5ab-07f8-47d1-ab0c-363639c1e8aa.xml, srb/ScsiPortLogError, storage.scsiportlogerror
req.header: srb.h
req.include-header: Miniport.h, Scsi.h
req.target-type: Desktop
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
req.lib: Scsiport.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - ScsiPortLogError
 - srb/ScsiPortLogError
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Scsiport.lib
 - Scsiport.dll
api_name:
 - ScsiPortLogError
---

# ScsiPortLogError function

## -description

The **ScsiPortLogError** routine logs errors to the system event log when a miniport driver or its HBA detects a SCSI error condition.

> [!NOTE]
> The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Use the [Storport driver](/windows-hardware/drivers/storage/storport-driver) and [Storport miniport](/windows-hardware/drivers/storage/storport-miniport-drivers) driver models instead.

## -parameters

### -param HwDeviceExtension

[in] Pointer to the hardware device extension. This is a per-HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the HBA's mapped access ranges. This area is available to the miniport driver in the **DeviceExtension->HwDeviceExtension** member of the HBA's device object immediately after the miniport driver calls [**ScsiPortInitialize**](nf-srb-scsiportinitialize.md). The port driver frees this memory when it removes the device.

### -param Srb

[in, optional] Pointer to a [SCSI request block](ns-srb-_scsi_request_block.md) if one is associated with the error. Otherwise, this parameter is **NULL**.

### -param PathId

[in] Identifies the SCSI bus.

### -param TargetId

[in] Identifies the target controller or device on the bus.

### -param Lun

[in] Identifies the logical unit number of the target device.

### -param ErrorCode

[in] Specifies an error code. This parameter can be one of the following values as the type of error.

| Value | Meaning |
| ----- | ------- |
| SP_BAD_FW_ERROR           | Indicates the driver has detected bad or old firmware. The device will not be used. |
| SP_BAD_FW_WARNING         | Indicates the driver has detected a card with old or bad firmware, which can result in reduced performance or functionality. |
| SP_BUS_PARITY_ERROR       | Indicates a SCSI bus parity error was detected. |
| SP_BUS_TIME_OUT           | Indicates a SCSI bus connection to a logical unit timed out. |
| SP_INTERNAL_ADAPTER_ERROR | Indicates an internal HBA error was detected. |
| SP_INVALID_RESELECTION    | Indicates a logical unit reselected unexpectedly or with an invalid queue tag. |
| SP_IRQ_NOT_RESPONDING     | Indicates the HBA is not interrupting when expected. |
| SP_PROTOCOL_ERROR         | Indicates the miniport driver detected a SCSI bus protocol error. |
| SP_REQUEST_TIMEOUT        | Indicates an operation to the controller has timed out. |
| SP_UNEXPECTED_DISCONNECT  | Indicates that a target disconnected unexpectedly. |

### -param UniqueId

[in] Specifies a unique identifier for the error. This value differentiates the current error from other errors with the same **ErrorCode**. For some miniport drivers, this identifies the line of code where the error was detected. For others, it is additional information returned by the HBA.

## -returns

None

## -remarks

A miniport driver should log all real hardware errors. However, it should not log common operational errors, such as selection time-outs or bus resets.

## -see-also

[**ScsiPortNotification**](nf-srb-scsiportnotification.md)
