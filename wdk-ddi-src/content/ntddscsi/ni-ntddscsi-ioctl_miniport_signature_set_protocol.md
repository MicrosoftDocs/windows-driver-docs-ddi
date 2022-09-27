---
UID: NI:ntddscsi.IOCTL_MINIPORT_SIGNATURE_SET_PROTOCOL
title: IOCTL_MINIPORT_SIGNATURE_SET_PROTOCOL
description: IOCTL_MINIPORT_SIGNATURE_SET_PROTOCOL is the signature used in conjunction with the IOCTL_SCSI_MINIPORT control code to send protocol-specific data to a miniport.
tech.root: storage
ms.date: 08/18/2022
keywords: ["IOCTL_MINIPORT_SIGNATURE_SET_PROTOCOL SIGNATURE"]
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
 - IOCTL_MINIPORT_SIGNATURE_SET_PROTOCOL
 - ntddscsi/IOCTL_MINIPORT_SIGNATURE_SET_PROTOCOL
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddscsi.h
api_name:
 - IOCTL_MINIPORT_SIGNATURE_SET_PROTOCOL
product:
 - Windows
---

# IOCTL_MINIPORT_SIGNATURE_SET_PROTOCOL SIGNATURE

## -description

**IOCTL_MINIPORT_SIGNATURE_SET_PROTOCOL** is the system-defined signature used in conjunction with the [**IOCTL_SCSI_MINIPORT**](ni-ntddscsi-ioctl_scsi_miniport.md) control code to send protocol-specific data to a miniport.

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

For this signature, [**IOCTL_SCSI_MINIPORT**](./ni-ntddscsi-ioctl_scsi_miniport.md) input buffer will contain an [**SRB_IO_CONTROL**](ns-ntddscsi-_srb_io_control.md) structure with:

* The **Signature** member set to IOCTL_MINIPORT_SIGNATURE_SET_PROTOCOL.

* The **ControlCode** member set to [**IOCTL_STORAGE_SET_PROPERTY**](../ntddstor/ni-ntddstor-ioctl_storage_set_property.md)

If the miniport recognizes and supports the **IOCTL_MINIPORT_SIGNATURE_SET_PROTOCOL** signature, it should update its device using the protocol information specified in a [**STORAGE_PROTOCOL_DATA_DESCRIPTOR**](../ntddstor/ns-ntddstor-_storage_protocol_data_descriptor.md)
structure. For this signature, the **STORAGE_PROTOCOL_DATA_DESCRIPTOR** structure is found in **IOCTL_SCSI_MINIPORT**'s input buffer immediately following the **SRB_IO_CONTROL** structure.

See [**IOCTL_SCSI_MINIPORT**](./ni-ntddscsi-ioctl_scsi_miniport.md) for information on how to calculate buffer sizes.


## -see-also

[**IOCTL_SCSI_MINIPORT**](ni-ntddscsi-ioctl_scsi_miniport.md)

[**IOCTL_STORAGE_SET_PROPERTY**](../ntddstor/ni-ntddstor-ioctl_storage_set_property.md)

[**STORAGE_PROTOCOL_DATA_DESCRIPTOR_EXT**](../ntddstor/ns-ntddstor-storage_protocol_data_descriptor_ext.md)

[**STORAGE_PROTOCOL_SPECIFIC_DATA_EXT**](../ntddstor/ns-ntddstor-storage_protocol_specific_data_ext.md)
