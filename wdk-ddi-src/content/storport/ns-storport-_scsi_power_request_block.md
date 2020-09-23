---
UID: NS:storport._SCSI_POWER_REQUEST_BLOCK
title: _SCSI_POWER_REQUEST_BLOCK (storport.h)
description: The SCSI_POWER_REQUEST_BLOCK structure is a special version of a SCSI_REQUEST_BLOCK that is used for power management requests.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsi_power_request_block.htm
tech.root: storage
ms.assetid: 04981b68-db32-461b-b24b-8b2bf2e53f78
ms.date: 03/29/2018
keywords: ["SCSI_POWER_REQUEST_BLOCK structure"]
ms.keywords: "*PSCSI_POWER_REQUEST_BLOCK, PSCSI_POWER_REQUEST_BLOCK, PSCSI_POWER_REQUEST_BLOCK structure pointer [Storage Devices], SCSI_POWER_REQUEST_BLOCK, SCSI_POWER_REQUEST_BLOCK structure [Storage Devices], _SCSI_POWER_REQUEST_BLOCK, storage.scsi_power_request_block, storport/PSCSI_POWER_REQUEST_BLOCK, storport/SCSI_POWER_REQUEST_BLOCK, structs-storport_de071b99-aa78-4c21-845e-f47b7d0297c0.xml"
req.header: storport.h
req.include-header: Storport.h, Minitape.h, Srb.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: SCSI_POWER_REQUEST_BLOCK, *PSCSI_POWER_REQUEST_BLOCK
f1_keywords:
 - _SCSI_POWER_REQUEST_BLOCK
 - storport/_SCSI_POWER_REQUEST_BLOCK
 - PSCSI_POWER_REQUEST_BLOCK
 - storport/PSCSI_POWER_REQUEST_BLOCK
 - SCSI_POWER_REQUEST_BLOCK
 - storport/SCSI_POWER_REQUEST_BLOCK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - SCSI_POWER_REQUEST_BLOCK
---

# _SCSI_POWER_REQUEST_BLOCK structure (storport.h)


## -description

The **SCSI_POWER_REQUEST_BLOCK** structure is a special version of a [**SCSI_REQUEST_BLOCK**](../srb/ns-srb-_scsi_request_block.md) that is used for power management requests.

> [!NOTE]
>
> The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the [Storport driver](/windows-hardware/drivers/storage/storport-driver) and [Storport miniport](/windows-hardware/drivers/storage/storport-miniport-drivers) driver models.

## -struct-fields

### -field Length

The size, in bytes, of the **SCSI_POWER_REQUEST_BLOCK** structure.

### -field Function

The operation to perform. For the **SCSI_POWER_REQUEST_BLOCK** structure, this member is always set to SRB_FUNCTION_POWER.

### -field SrbStatus

The status of the completed request. This member should be set by the miniport driver before it notifies the Storport driver that the request has completed. A miniport driver notifies the Storport driver that the request has completed by calling the [**StorPortNotification**](nf-storport-storportnotification.md) function with the **RequestComplete** notification type.

See [**SCSI_REQUEST_BLOCK**](../srb/ns-srb-_scsi_request_block.md) in the WDK documentation for a list of possible values for this member.

### -field SrbPowerFlags

The power management flags. Currently, the only flag allowed is SRB_POWER_FLAGS_ADAPTER_REQUEST, which indicates that the power management request is for the adapter. If this flag is set, the miniport driver should ignore the values in the **PathId**, **TargetId**, and **Lun**.

### -field PathId

The SCSI port or bus identifier for the request. This value is zero based.

### -field TargetId

The target controller or device identifier on the bus.

### -field Lun

The logical unit number (LUN) of the device.

### -field DevicePowerState

An enumerator value of type [**STOR_DEVICE_POWER_STATE**](ne-storport-_stor_device_power_state.md) that specifies the requested power state of the device.

### -field SrbFlags

Miniport driver should ignore this member.

### -field DataTransferLength

Miniport driver should ignore this member.

### -field TimeOutValue

The interval, in seconds, that the request can execute before the Storport driver determines that the request has timed out.

### -field DataBuffer

Miniport driver should ignore this member.

### -field SenseInfoBuffer

Miniport driver should ignore this member.

### -field NextSrb

Miniport driver should ignore this member.

### -field OriginalRequest

Miniport driver should ignore this member.

### -field SrbExtension

A pointer to the SRB extension. A miniport driver must not use this member if it set **SrbExtensionSize** to zero in the [**HW_INITIALIZATION_DATA**](ns-storport-_hw_initialization_data~r1.md) structure. The Storport driver does not initialize the memory that this member points to. The HBA can directly access the data that the miniport driver writes into the SRB extension. A miniport driver can obtain the physical address of the SRB extension by calling the [**StorPortGetPhysicalAddress**](nf-storport-storportgetphysicaladdress.md) routine.

### -field PowerAction

An enumerator value of type [**STOR_POWER_ACTION**](ne-storport-stor_power_action.md) that specifies the type of system shutdown that is about to occur. This value is meaningful only if the device is moving into the D1, D2, or D3 power state as indicated by the **DevicePowerState** member.

### -field Reserved

Reserved for system use.

### -field Reserved5

Reserved for system use.

## -remarks

The Storport driver calls [**HwStorBuildIo**](nc-storport-hw_buildio.md) to pass SRBs to the miniport driver. **HwStorBuildIo** should check the **Function** member of the SRB to determine the type of the SRB. If the **Function** member is set to SRB_FUNCTION_POWER, the SRB is a structure of type **SCSI_POWER_REQUEST_BLOCK**.

The Storport driver sends **SCSI_POWER_REQUEST_BLOCK** requests to a miniport driver to notify the miniport driver of Windows power events that affect storage devices that are connected to the adapter. In the case of a power up event, this request gives the miniport driver an opportunity to initialize itself. In the case of a hibernation or shutdown event, this request gives the miniport driver an opportunity to complete I/O requests and prepare for a power down. The miniport driver can use the value in the **PowerAction** member of the **SCSI_POWER_REQUEST_BLOCK** to determine what actions are required. After the miniport driver completes the **SCSI_POWER_REQUEST_BLOCK** request, the Storport driver calls [**HwScsiAdapterControl**](/previous-versions/windows/hardware/drivers/ff557274(v=vs.85)) with a control request of **ScsiStopAdapter** to power down the adapter. The miniport driver reinitialize while processing the SRB_FUNCTION_POWER request, or it can wait and reinitialize when the Storport driver calls [**HwStorAdapterControl**](nc-storport-hw_adapter_control.md) to perform a an **ScsiRestartAdapter** control request.

 When transitioning from the D0 power state to a lower-powered state (D1, D2, or D3) the Storport driver sends a **SCSI_POWER_REQUEST_BLOCK** request to the miniport driver before the underlying bus driver powers down the adapter.

The following conditions must exist before the Storport driver will send a **SCSI_POWER_REQUEST_BLOCK** request to the miniport driver:

* The adapter is not stopped.
* The I/O queue for the adapter is paused.
* The adapter hardware is powered up.
* The miniport can access the adapter's hardware resources.

## -see-also

[**HwStorBuildIo**](nc-storport-hw_buildio.md)

[**SCSI_REQUEST_BLOCK**](../srb/ns-srb-_scsi_request_block.md)

[**StorPortNotification**](hnf-storport-storportnotification.md)