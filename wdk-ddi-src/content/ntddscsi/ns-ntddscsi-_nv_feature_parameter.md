---
UID: NS:ntddscsi._NV_FEATURE_PARAMETER
title: NV_FEATURE_PARAMETER (ntddscsi.h)
description: The NV_FEATURE_PARAMETER structure is used in conjunction with the IOCTL_SCSI_MINIPORT_NVCACHE request to get NV Cache Manager feature support information from the device.
old-location: storage\nv_feature_parameter.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["NV_FEATURE_PARAMETER structure"]
ms.keywords: "*PNV_FEATURE_PARAMETER, NV_FEATURE_PARAMETER, NV_FEATURE_PARAMETER structure [Storage Devices], PNV_FEATURE_PARAMETER, PNV_FEATURE_PARAMETER structure pointer [Storage Devices], _NV_FEATURE_PARAMETER, ntddscsi/NV_FEATURE_PARAMETER, ntddscsi/PNV_FEATURE_PARAMETER, storage.nv_feature_parameter, structs-nvcache_ac844d4b-783b-4248-8699-353eef5a3d52.xml"
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
req.typenames: NV_FEATURE_PARAMETER, *PNV_FEATURE_PARAMETER
f1_keywords:
 - _NV_FEATURE_PARAMETER
 - ntddscsi/_NV_FEATURE_PARAMETER
 - PNV_FEATURE_PARAMETER
 - ntddscsi/PNV_FEATURE_PARAMETER
 - NV_FEATURE_PARAMETER
 - ntddscsi/NV_FEATURE_PARAMETER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddscsi.h
api_name:
 - NV_FEATURE_PARAMETER
---

# NV_FEATURE_PARAMETER structure

## -description

The NV_FEATURE_PARAMETER structure is used in conjunction with the [**IOCTL_SCSI_MINIPORT_NVCACHE**](./ni-ntddscsi-ioctl_scsi_miniport_nvcache.md) request to get NV Cache Manager feature support information from the device. The NV Cache Manager feature parameters structure is returned by the miniport driver upon the successful return from the NRB_NVCACHE_INFO function, as requested in the Function field of the [**NVCACHE_REQUEST_BLOCK**](./ns-ntddscsi-_nvcache_request_block.md) structure.

The values in these fields come from the IDENTIFY DEVICE command in section 7.16 of the ATA8-ACS specification.

## -struct-fields

### -field NVPowerModeEnabled

Taken from word 214, bit 0 of the IDENTIFY DEVICE data, a value of one means the NV Cache Power Mode feature set is enabled.

### -field NVParameterReserv1

Reserved for future use.

### -field NVCmdEnabled

Taken from word 214, bit 4 of the IDENTIFY DEVICE data, a value of one means the NV Cache feature set is enabled.

### -field NVParameterReserv2

Reserved for future use.

### -field NVPowerModeVer

Taken from word 214, bits 8 through 11 of the IDENTIFY DEVICE data, this field contains the NV Cache Power Mode feature set version.

### -field NVCmdVer

Taken from word 214, bits 12 through 15 of the IDENTIFY DEVICE data, this field contains the NV Cache feature set version.

### -field NVSize

Taken from words 215 and 216 of the IDENTIFY DEVICE data, this field contains the NV Cache Size, in logical blocks.

### -field NVReadSpeed

Taken from word 217 of the IDENTIFY DEVICE data, this field contains the NV Cache Read Transfer Speed, in megabytes per second (MB/s).

### -field NVWrtSpeed

Taken from word 218 of the IDENTIFY DEVICE data, this field contains the NV Cache Write Transfer Speed, in megabytes per second (MB/s).

### -field DeviceSpinUpTime

Taken from word 219, bits 0 through 7 of the IDENTIFY DEVICE data, this field contains the device's estimated time to spin up, in seconds.

## -see-also

[**IOCTL_SCSI_MINIPORT_NVCACHE**](./ni-ntddscsi-ioctl_scsi_miniport_nvcache.md)

[**NVCACHE_REQUEST_BLOCK**](./ns-ntddscsi-_nvcache_request_block.md)
