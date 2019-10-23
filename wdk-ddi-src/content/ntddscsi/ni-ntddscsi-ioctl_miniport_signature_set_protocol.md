---
UID: NI:ntddscsi.IOCTL_MINIPORT_SIGNATURE_SET_PROTOCOL
title: IOCTL_MINIPORT_SIGNATURE_SET_PROTOCOL
author: windows-driver-content
description: IOCTL_MINIPORT_SIGNATURE_SET_PROTOCOL is the signature used in conjunction with the IOCTL_SCSI_MINIPORT control code to send protocol-specific data to a miniport. 
tech.root: storage
ms.assetid: 271794f2-20f8-410d-b6fb-b624f3cb38b2
ms.author: windowsdriverdev
ms.date: 03/07/2019
ms.topic: ioctl
f1_keywords:
 - "ntddscsi/IOCTL_MINIPORT_SIGNATURE_SET_PROTOCOL"
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
targetos: Windows
ms.custom: 19H1
---

# IOCTL_MINIPORT_SIGNATURE_SET_PROTOCOL SIGNATURE

## -description

IOCTL_MINIPORT_SIGNATURE_SET_PROTOCOL is the signature used in conjunction with the [IOCTL_SCSI_MINIPORT](ni-ntddscsi-ioctl_scsi_miniport.md) control code to send protocol-specific data to a miniport.

## -remarks

For this signature, IOCTL_SCSI_MINIPORT's input buffer will contain an [SRB_IO_CONTROL](ns-ntddscsi-_srb_io_control.md) structure with:

* The **Signature** member is set to IOCTL_MINIPORT_SIGNATURE_SET_PROTOCOL

* The **ControlCode** member is set to [IOCTL_STORAGE_SET_PROPERTY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_set_property)

If the miniport recognizes and supports the IOCTL_MINIPORT_SIGNATURE_SET_PROTOCOL signature, it should update its device using the protocol information specified in a [STORAGE_PROTOCOL_DATA_DESCRIPTOR](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_protocol_data_descriptor)
structure. For this signature, the STORAGE_PROTOCOL_DATA_DESCRIPTOR structure is found in IOCTL_SCSI_MINIPORT's input buffer immediately following the SRB_IO_CONTROL structure.

## -see-also

[IOCTL_SCSI_MINIPORT](ni-ntddscsi-ioctl_scsi_miniport.md)

[IOCTL_STORAGE_SET_PROPERTY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_set_property)

[STORAGE_PROTOCOL_DATA_DESCRIPTOR_EXT](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-storage_protocol_data_descriptor_ext)

[STORAGE_PROTOCOL_SPECIFIC_DATA_EXT](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-storage_protocol_specific_data_ext)
