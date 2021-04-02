---
UID: NS:ntddstor._DEVICE_MEDIA_INFO
title: _DEVICE_MEDIA_INFO (ntddstor.h)
description: A storage class driver returns an array of DEVICE_MEDIA_INFO structures, embedded in a GET_MEDIA_TYPES structure, in response to an IOCTL_STORAGE_GET_MEDIA_TYPES_EX device-control request.
old-location: storage\device_media_info.htm
tech.root: storage
ms.date: 04/01/2021
keywords: ["DEVICE_MEDIA_INFO structure"]
ms.keywords: "*PDEVICE_MEDIA_INFO, DEVICE_MEDIA_INFO, DEVICE_MEDIA_INFO structure [Storage Devices], MEDIA_CURRENTLY_MOUNTED, MEDIA_ERASEABLE, MEDIA_READ_ONLY, MEDIA_READ_WRITE, MEDIA_WRITE_ONCE, MEDIA_WRITE_PROTECTED, PDEVICE_MEDIA_INFO, PDEVICE_MEDIA_INFO structure pointer [Storage Devices], _DEVICE_MEDIA_INFO, ntddstor/DEVICE_MEDIA_INFO, ntddstor/PDEVICE_MEDIA_INFO, storage.device_media_info, structs-general_e2c363ff-f053-45be-a807-f90480c0ae1f.xml"
req.header: ntddstor.h
req.include-header: Ntddstor.h, Minitape.h
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
req.typenames: DEVICE_MEDIA_INFO, *PDEVICE_MEDIA_INFO
f1_keywords:
 - _DEVICE_MEDIA_INFO
 - ntddstor/_DEVICE_MEDIA_INFO
 - PDEVICE_MEDIA_INFO
 - ntddstor/PDEVICE_MEDIA_INFO
 - DEVICE_MEDIA_INFO
 - ntddstor/DEVICE_MEDIA_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _DEVICE_MEDIA_INFO
 - PDEVICE_MEDIA_INFO
 - DEVICE_MEDIA_INFO
---

# _DEVICE_MEDIA_INFO structure (ntddstor.h)

## -description

A storage class driver returns an array of **DEVICE_MEDIA_INFO** structures, embedded in a [**GET_MEDIA_TYPES**](ns-ntddstor-_get_media_types.md) structure, in response to an [**IOCTL_STORAGE_GET_MEDIA_TYPES_EX**](ni-ntddstor-ioctl_storage_get_media_types_ex.md) device-control request.

## -struct-fields

### -field DeviceSpecific

### -field DeviceSpecific.DiskInfo

Describes a nonremovable (fixed) disk.

### -field DeviceSpecific.DiskInfo.Cylinders

Specifies the number of cylinders on this disk.

### -field DeviceSpecific.DiskInfo.MediaType

Specifies a [**MEDIA_TYPE**](/previous-versions/windows/hardware/drivers/ff562216(v=vs.85)) of **FixedMedia**.

### -field DeviceSpecific.DiskInfo.TracksPerCylinder

Specifies the number of tracks per cylinder.

### -field DeviceSpecific.DiskInfo.SectorsPerTrack

Specifies the number of sectors per track.

### -field DeviceSpecific.DiskInfo.BytesPerSector

Specifies the number of bytes per sector.

### -field DeviceSpecific.DiskInfo.NumberMediaSides

Specifies the number of sides of the disk that can contain data: either 1 for one-sided media or 2 for two-sided media.

### -field DeviceSpecific.DiskInfo.MediaCharacteristics

Specifies characteristics of the disk indicated by one or more of the following flags.

* MEDIA_ERASEABLE         0x00000001
* MEDIA_WRITE_ONCE        0x00000002
* MEDIA_READ_ONLY         0x00000004
* MEDIA_READ_WRITE        0x00000008
* MEDIA_WRITE_PROTECTED   0x00000100
* MEDIA_CURRENTLY_MOUNTED 0x80000000

### -field DeviceSpecific.RemovableDiskInfo

Describes a removable (nonfixed) disk.

### -field DeviceSpecific.RemovableDiskInfo.Cylinders

Specifies the number of cylinders on this disk.

### -field DeviceSpecific.RemovableDiskInfo.MediaType

Specifies a [**MEDIA_TYPE**](/previous-versions/windows/hardware/drivers/ff562216(v=vs.85)) or [**STORAGE_MEDIA_TYPE**](ne-ntddstor-_storage_media_type.md) value that indicates the type of removable disk.

### -field DeviceSpecific.RemovableDiskInfo.TracksPerCylinder

Specifies the number of tracks per cylinder.

### -field DeviceSpecific.RemovableDiskInfo.SectorsPerTrack

Specifies the number of sectors per track.

### -field DeviceSpecific.RemovableDiskInfo.BytesPerSector

Specifies the number of bytes per sector.

### -field DeviceSpecific.RemovableDiskInfo.NumberMediaSides

Specifies the number of sides of the disk that can contain data: 1 for one-sided media or 2 for two-sided media.

### -field DeviceSpecific.RemovableDiskInfo.MediaCharacteristics

Specifies characteristics of the disk, indicated by MEDIA_*XXX* flags ORed together. For a list of these flags, see the **DeviceSpecific.DiskInfo.MediaCharacteristics** member of the **DeviceSpecific.DiskInfo** structure.

### -field DeviceSpecific.TapeInfo

Describes a tape.

### -field DeviceSpecific.TapeInfo.MediaType

Specifies a [**STORAGE_MEDIA_TYPE**](ne-ntddstor-_storage_media_type.md) value that indicates the type of tape described in this structure.

### -field DeviceSpecific.TapeInfo.MediaCharacteristics

Specifies characteristics of the tape, indicated by MEDIA_*XXX* flags ORed together. For a list of these flags, see the **DeviceSpecific.DiskInfo.MediaCharacteristics** member of the **DeviceSpecific.DiskInfo** structure.

### -field DeviceSpecific.TapeInfo.CurrentBlockSize

Specifies the current block size, in bytes.

### -field DeviceSpecific.TapeInfo.BusType

Specifies a value of type [**STORAGE_BUS_TYPE**](ne-ntddstor-storage_bus_type.md) that indicates the bus type.

### -field DeviceSpecific.TapeInfo.BusSpecificData

### -field DeviceSpecific.TapeInfo.BusSpecificData.ScsiInformation

Specifies bus-specific information from mode page data that describes the medium supported by the tape drive. Values for other bus types will be supplied in a later release.

### -field DeviceSpecific.TapeInfo.BusSpecificData.ScsiInformation.MediumType

Specifies the SCSI-specific medium type.

### -field DeviceSpecific.TapeInfo.BusSpecificData.ScsiInformation.DensityCode

Specifies the SCSI-specific current operating density for read/write operations.

## -remarks

This structure is used by a storage driver to indicate the types of media supported by a device and which type is currently mounted, if any. A driver must provide this information if it might control drives in a media library or changer or if its device might be accessed by the Removable Storage Manager (RSM).

The driver fills in an array of **DEVICE_MEDIA_INFO** structures, one for each medium type supported by the device, embedded in a [**GET_MEDIA_TYPES**](ns-ntddstor-_get_media_types.md) structure.

## -see-also

[**STORAGE_MEDIA_TYPE**](ne-ntddstor-_storage_media_type.md)

[**TapeMiniGetMediaTypes**](../minitape/nc-minitape-tape_process_command_routine.md)
