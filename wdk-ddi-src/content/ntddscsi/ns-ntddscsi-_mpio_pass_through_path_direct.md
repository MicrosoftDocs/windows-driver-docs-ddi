---
UID: NS:ntddscsi._MPIO_PASS_THROUGH_PATH_DIRECT
title: MPIO_PASS_THROUGH_PATH_DIRECT (ntddscsi.h)
description: The MPIO_PASS_THROUGH_PATH_DIRECT structure is used together with an IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT request to instruct the port driver to send an embedded SCSI command to the target device.
old-location: storage\mpio_pass_through_path_direct.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["MPIO_PASS_THROUGH_PATH_DIRECT structure"]
ms.keywords: "*PMPIO_PASS_THROUGH_PATH_DIRECT, MPIO_PASS_THROUGH_PATH_DIRECT, MPIO_PASS_THROUGH_PATH_DIRECT structure [Storage Devices], PMPIO_PASS_THROUGH_PATH_DIRECT, PMPIO_PASS_THROUGH_PATH_DIRECT structure pointer [Storage Devices], _MPIO_PASS_THROUGH_PATH_DIRECT, ntddscsi/MPIO_PASS_THROUGH_PATH_DIRECT, ntddscsi/PMPIO_PASS_THROUGH_PATH_DIRECT, storage.mpio_pass_through_path_direct, structs-scsibus_54825e13-2114-46d8-ab0f-84feb86b8f5c.xml"
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
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
req.typenames: MPIO_PASS_THROUGH_PATH_DIRECT, *PMPIO_PASS_THROUGH_PATH_DIRECT
f1_keywords:
 - _MPIO_PASS_THROUGH_PATH_DIRECT
 - ntddscsi/_MPIO_PASS_THROUGH_PATH_DIRECT
 - PMPIO_PASS_THROUGH_PATH_DIRECT
 - ntddscsi/PMPIO_PASS_THROUGH_PATH_DIRECT
 - MPIO_PASS_THROUGH_PATH_DIRECT
 - ntddscsi/MPIO_PASS_THROUGH_PATH_DIRECT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddscsi.h
api_name:
 - _MPIO_PASS_THROUGH_PATH_DIRECT
 - PMPIO_PASS_THROUGH_PATH_DIRECT
 - MPIO_PASS_THROUGH_PATH_DIRECT
---

# MPIO_PASS_THROUGH_PATH_DIRECT structure

## -description

The **MPIO_PASS_THROUGH_PATH_DIRECT** structure is used together with an [**IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT**](ni-ntddscsi-ioctl_mpio_pass_through_path_direct.md) request to instruct the port driver to send an embedded SCSI command to the target device.

## -struct-fields

### -field PassThrough

Contains a [**SCSI_PASS_THROUGH_DIRECT**](ns-ntddscsi-_scsi_pass_through_direct.md) structure that is set up in the same way as it is for an [**IOCTL_SCSI_PASS_THROUGH_DIRECT**](ni-ntddscsi-ioctl_scsi_pass_through_direct.md) request.

### -field Version

Set to zero.

### -field Length

The size of the **MPIO_PASS_THROUGH_PATH_DIRECT** structure, in bytes.

### -field Flags

Can be a mask of the following values:

* MPIO_IOCTL_FLAG_USE_SCSIADDRESS OR MPIO_IOCTL_FLAG_USE_PATHID
* MPIO_IOCTL_FLAG_INVOLVE_DSM

### -field PortNumber

The port number if MPIO_IOCTL_FLAG_USE_SCSIADDRESS is set. Otherwise, this member is zero. If MPIO_IOCTL_FLAG_USE_SCSIADDRESS is set, the **PathId** and **TargetId** values are taken from the embedded [**SCSI_PASS_THROUGH_DIRECT**](ns-ntddscsi-_scsi_pass_through_direct.md) structure.

### -field MpioPathId

The **PathId** for the real LUN. This value can be obtained by using a WMI request for the PDO_INFORMATION that is associated with the real LUN. This value is set only if MPIO_IOCTL_FLAG_USE_PATHID is set.

## -remarks

The **MPIO_PASS_THROUGH_PATH_DIRECT** structure is used for a single-buffered device control request. To use double-buffering, callers should use [**IOCTL_MPIO_PASS_THROUGH_PATH**](ni-ntddscsi-ioctl_mpio_pass_through_path.md).

## -see-also

[**IOCTL_MPIO_PASS_THROUGH_PATH**](ni-ntddscsi-ioctl_mpio_pass_through_path.md)

[**IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT**](ni-ntddscsi-ioctl_mpio_pass_through_path_direct.md)

[**IOCTL_SCSI_PASS_THROUGH**](ni-ntddscsi-ioctl_scsi_pass_through.md)

[**IOCTL_SCSI_PASS_THROUGH_DIRECT**](ni-ntddscsi-ioctl_scsi_pass_through_direct.md)

[**SCSI_PASS_THROUGH**](ns-ntddscsi-_scsi_pass_through.md)

[**SCSI_REQUEST_BLOCK**](../srb/ns-srb-_scsi_request_block.md)
