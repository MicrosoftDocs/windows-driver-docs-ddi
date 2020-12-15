---
UID: NS:minitape._TAPE_SET_DRIVE_PARAMETERS
title: _TAPE_SET_DRIVE_PARAMETERS (minitape.h)
description: The TAPE_SET_DRIVE_PARAMETERS structure is used in conjunction with the IOCTL_TAPE_SET_DRIVE_PARAMS request to adjust the configurable parameters of a tape drive.
old-location: storage\tape_set_drive_parameters.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["TAPE_SET_DRIVE_PARAMETERS structure"]
ms.keywords: "*PTAPE_SET_DRIVE_PARAMETERS, PTAPE_SET_DRIVE_PARAMETERS, PTAPE_SET_DRIVE_PARAMETERS structure pointer [Storage Devices], TAPE_SET_DRIVE_PARAMETERS, TAPE_SET_DRIVE_PARAMETERS structure [Storage Devices], _TAPE_SET_DRIVE_PARAMETERS, ntddtape/PTAPE_SET_DRIVE_PARAMETERS, ntddtape/TAPE_SET_DRIVE_PARAMETERS, storage.tape_set_drive_parameters, structs-tape_621b7e53-4f98-4fad-9f75-28420dc78031.xml"
req.header: minitape.h
req.include-header: Ntddtape.h, Minitape.h
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
req.typenames: TAPE_SET_DRIVE_PARAMETERS, *PTAPE_SET_DRIVE_PARAMETERS
f1_keywords:
 - _TAPE_SET_DRIVE_PARAMETERS
 - minitape/_TAPE_SET_DRIVE_PARAMETERS
 - PTAPE_SET_DRIVE_PARAMETERS
 - minitape/PTAPE_SET_DRIVE_PARAMETERS
 - TAPE_SET_DRIVE_PARAMETERS
 - minitape/TAPE_SET_DRIVE_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddtape.h
api_name:
 - TAPE_SET_DRIVE_PARAMETERS
---

# _TAPE_SET_DRIVE_PARAMETERS structure (minitape.h)


## -description

The TAPE_SET_DRIVE_PARAMETERS structure is used in conjunction with the <a href="/windows-hardware/drivers/ddi/ntddtape/ni-ntddtape-ioctl_tape_set_drive_params">IOCTL_TAPE_SET_DRIVE_PARAMS</a> request to adjust the configurable parameters of a tape drive.

## -struct-fields

### -field ECC

When set to <b>TRUE</b>, instructs the device to use hardware error correction. When <b>FALSE</b>, the device does not use hardware error correction.

### -field Compression

When set to <b>TRUE</b>, instructs the device to compress data prior to writing it. If a drive must be at beginning of partition before it can set compression (TAPE_DRIVE_SET_CMP_BOP_ONLY), the caller is responsible for positioning the drive before attempting to set compression. When <b>FALSE</b>, the device does not compress data prior to writing it.

### -field DataPadding

When set to <b>TRUE</b>, instructs the device to pad data with zeros. This is to keep the tape streaming until data is ready. When <b>FALSE</b>, the device does not pad data with zeros.

### -field ReportSetmarks

When set to <b>TRUE</b>, instructs the device to report setmarks encountered during read or space operations. When <b>FALSE</b>, the device does not report setmarks encountered during read or space operations.

### -field EOTWarningZoneSize

Indicates the size in bytes of the early warning zone toward the end of the tape in which the drive returns a check condition when it enters the zone.

## -remarks

The miniclass driver can ignore parameters its device does not support. The calling application is responsible for determining whether a device supports a particular feature before attempting to set it.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddtape/ni-ntddtape-ioctl_tape_set_drive_params">IOCTL_TAPE_SET_DRIVE_PARAMS</a>



<a href="/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniSetDriveParameters</a>
