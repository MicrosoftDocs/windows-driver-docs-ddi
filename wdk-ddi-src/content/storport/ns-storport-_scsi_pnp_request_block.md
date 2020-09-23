---
UID: NS:storport._SCSI_PNP_REQUEST_BLOCK
title: _SCSI_PNP_REQUEST_BLOCK (storport.h)
description: TheSCSI_PNP_REQUEST_BLOCK structure is a special version of a SCSI_REQUEST_BLOCK that is used for plug and play (PNP) requests.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsi_pnp_request_block.htm
tech.root: storage
ms.assetid: 0627065b-62c2-4df8-973c-b4fb5811296e
ms.date: 03/29/2018
keywords: ["SCSI_PNP_REQUEST_BLOCK structure"]
ms.keywords: "*PSCSI_PNP_REQUEST_BLOCK, PSCSI_PNP_REQUEST_BLOCK, PSCSI_PNP_REQUEST_BLOCK structure pointer [Storage Devices], SCSI_PNP_REQUEST_BLOCK, SCSI_PNP_REQUEST_BLOCK structure [Storage Devices], StorFilterResourceRequirements, StorQueryCapabilities, StorQueryResourceRequirements, StorRemoveDevice, StorStartDevice, StorStopDevice, StorSupriseRemoval, _SCSI_PNP_REQUEST_BLOCK, storage.scsi_pnp_request_block, storport/PSCSI_PNP_REQUEST_BLOCK, storport/SCSI_PNP_REQUEST_BLOCK, structs-storport_d08ea849-f1d6-4584-b6a4-df7127f6873d.xml"
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
req.typenames: SCSI_PNP_REQUEST_BLOCK, *PSCSI_PNP_REQUEST_BLOCK
f1_keywords:
 - _SCSI_PNP_REQUEST_BLOCK
 - storport/_SCSI_PNP_REQUEST_BLOCK
 - PSCSI_PNP_REQUEST_BLOCK
 - storport/PSCSI_PNP_REQUEST_BLOCK
 - SCSI_PNP_REQUEST_BLOCK
 - storport/SCSI_PNP_REQUEST_BLOCK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - SCSI_PNP_REQUEST_BLOCK
---

# _SCSI_PNP_REQUEST_BLOCK structure (storport.h)


## -description

The**SCSI_PNP_REQUEST_BLOCK** structure is a special version of a [**SCSI_REQUEST_BLOCK**](../srb/ns-srb-_scsi_request_block.md) that is used for plug and play (PNP) requests.

> [!NOTE]
>
> The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the [Storport driver](/windows-hardware/drivers/storage/storport-driver) and [Storport miniport driver](/windows-hardware/drivers/storage/storport-miniport-drivers) models.

## -struct-fields

### -field Length

The size, in bytes, of the **SCSI_PNP_REQUEST_BLOCK** structure.

### -field Function

The operation to perform. For the **SCSI_PNP_REQUEST_BLOCK** structure, this member is always set to SRB_FUNCTION_PNP.

### -field SrbStatus

The status of the completed request. The miniport driver should set this value before notifying the Storport driver that the request has completed. A miniport driver notifies the Storport driver that the request has completed by calling the [**StorPortNotification**](..nf-storport-storportnotification.md) routine with a notification type of **RequestComplete**. For a list of possible status values, see [**SCSI_REQUEST_BLOCK**](../srb/ns-srb-_scsi_request_block.md).

### -field PnPSubFunction

This member is not currently used. Miniport drivers ignore this member.

### -field PathId

The SCSI port or bus identifier for the request. This value is zero based.

### -field TargetId

The target controller or device identifier on the bus.

### -field Lun

The logical unit number (LUN) of the device.

### -field PnPAction

The plug and play action to perform. This member can have one of the following values:

| Value | Meaning |
| ----- | ------- |
| **StorStartDevice** (0x00)                | Start the device.  |
| **StorRemoveDevice** (0x02)               | Remove the device. |
| **StorStopDevice** (0x04)                 | Stop the device.   |
| **StorQueryCapabilities** (0x09)          | Query the capabilities of the device. |
| **StorQueryResourceRequirements** (0x0B)  | Query the resource requirements for the device. |
| **StorFilterResourceRequirements** (0x0D) | Filter the resource requirements for the device. |
| **StorSupriseRemoval** (0x17)             | Surprise Removal of the device. This value was added in Windows 7. |

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

### -field SrbPnPFlags

The PNP flags. Currently, the only flag allowed is SRB_PNP_FLAGS_ADAPTER_REQUEST, which indicates that the PNP request is for the adapter, and not for one of the devices on the adapter. If this flag is set, the miniport driver should ignore the values in the **PathId**, **TargetId**, and **Lun**.

### -field Reserved

Reserved for system use.

### -field Reserved4

Reserved for system use.

## -remarks

The Storport driver sends **SCSI_PNP_REQUEST_BLOCK** requests to a miniport driver to notify the miniport driver of Windows plug and play events that affect storage devices that are connected to the adapter.

The Storport driver calls [**HwStorBuildIo**](nc-storport-hw_buildio.md) to pass SRBs to the miniport driver. **HwStorBuildIo** checks the **Function** member of the SRB to determine the type of the SRB. If the **Function** member is set to SRB_FUNCTION_PNP, the SRB is a structure of type **SCSI_PNP_REQUEST_BLOCK**.

## -see-also

[**HwStorBuildIo**](nc-storport-hw_buildio.md)

[**SCSI_REQUEST_BLOCK**](../srb/ns-srb-_scsi_request_block.md)

[**StorPortNotification**](nf-storport-storportnotification.md)