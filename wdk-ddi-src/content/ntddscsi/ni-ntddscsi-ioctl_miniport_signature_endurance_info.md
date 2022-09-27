---
UID: NI:ntddscsi.IOCTL_MINIPORT_SIGNATURE_ENDURANCE_INFO
title: IOCTL_MINIPORT_SIGNATURE_ENDURANCE_INFO
description: IOCTL_MINIPORT_SIGNATURE_ENDURANCE_INFO is the system-defined signature used in conjunction with the IOCTL_SCSI_MINIPORT control code to request that a miniport return endurance data for a target device.
tech.root: storage
ms.date: 08/18/2022
keywords: ["IOCTL_MINIPORT_SIGNATURE_ENDURANCE_INFO SIGNATURE"]
req.header: ntddscsi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.max-support: 
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - IOCTL_MINIPORT_SIGNATURE_ENDURANCE_INFO
 - ntddscsi/IOCTL_MINIPORT_SIGNATURE_ENDURANCE_INFO
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddscsi.h
api_name:
 - IOCTL_MINIPORT_SIGNATURE_ENDURANCE_INFO
product:
 - Windows
---

# IOCTL_MINIPORT_SIGNATURE_ENDURANCE_INFO SIGNATURE

## -description

**IOCTL_MINIPORT_SIGNATURE_ENDURANCE_INFO** is the system-defined *signature* used in conjunction with the [**IOCTL_SCSI_MINIPORT**](./ni-ntddscsi-ioctl_scsi_miniport.md) control code to request that a miniport return a target device's endurance information.

## -ioctlparameters

### -input-buffer

See Remarks.

### -input-buffer-length

See Remarks.

### -output-buffer

See Remarks.

### -output-buffer-length

See Remarks.

### -in-out-buffer

None.

### -inout-buffer-length

Not applicable.

### -status-block

Not applicable.

## -remarks

For this signature, [**IOCTL_SCSI_MINIPORT**](./ni-ntddscsi-ioctl_scsi_miniport.md)'s input buffer will contain an [**SRB_IO_CONTROL**](ns-ntddscsi-_srb_io_control.md) structure with:

* The **Signature** member is set to IOCTL_MINIPORT_SIGNATURE_ENDURANCE_INFO.

* The **ControlCode** member is set to [**IOCTL_STORAGE_QUERY_PROPERTY**](../ntddstor/ni-ntddstor-ioctl_storage_query_property.md).

If the miniport recognizes and supports the **IOCTL_MINIPORT_SIGNATURE_ENDURANCE_INFO** signature, it should return its device's endurance data in a [**STORAGE_ENDURANCE_DATA_DESCRIPTOR**](ns-ntddscsi-storage_endurance_data_descriptor.md) structure. Specifically, **IOCTL_SCSI_MINIPORT**'s output buffer will contain an **SRB_IO_CONTROL** structure, followed immediately by a **STORAGE_ENDURANCE_DATA_DESCRIPTOR** structure that contains the endurance data.

See [**IOCTL_SCSI_MINIPORT**](./ni-ntddscsi-ioctl_scsi_miniport.md) for information on how to calculate buffer sizes.

## -see-also

[**IOCTL_SCSI_MINIPORT**](./ni-ntddscsi-ioctl_scsi_miniport.md)

[**IOCTL_STORAGE_QUERY_PROPERTY**](../ntddstor/ni-ntddstor-ioctl_storage_query_property.md)

[**STORAGE_ENDURANCE_DATA_DESCRIPTOR**](ns-ntddscsi-storage_endurance_data_descriptor.md)
