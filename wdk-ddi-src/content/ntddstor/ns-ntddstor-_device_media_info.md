---
UID: NS:ntddstor._DEVICE_MEDIA_INFO
title: _DEVICE_MEDIA_INFO
author: windows-driver-content
description: A storage class driver returns an array of DEVICE_MEDIA_INFO structures, embedded in a GET_MEDIA_TYPES structure, in response to an IOCTL_STORAGE_GET_MEDIA_TYPES_EX device-control request.
old-location: storage\device_media_info.htm
old-project: storage
ms.assetid: 87906511-7bcb-4f4d-9383-44b0501536e3
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _DEVICE_MEDIA_INFO, DEVICE_MEDIA_INFO, *PDEVICE_MEDIA_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DEVICE_MEDIA_INFO
req.alt-loc: ntddstor.h
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
req.typenames: DEVICE_MEDIA_INFO, *PDEVICE_MEDIA_INFO
---

# _DEVICE_MEDIA_INFO structure



## -description
A storage class driver returns an array of <b>DEVICE_MEDIA_INFO</b> structures, embedded in a <a href="..\ntddstor\ns-ntddstor-_get_media_types.md">GET_MEDIA_TYPES</a> structure, in response to an <a href="..\ntddstor\ni-ntddstor-ioctl_storage_get_media_types_ex.md">IOCTL_STORAGE_GET_MEDIA_TYPES_EX</a> device-control request.



## -syntax

````
typedef struct _DEVICE_MEDIA_INFO {
  union {
    struct {
      LARGE_INTEGER      Cylinders;
      STORAGE_MEDIA_TYPE MediaType;
      ULONG              TracksPerCylinder;
      ULONG              SectorsPerTrack;
      ULONG              BytesPerSector;
      ULONG              NumberMediaSides;
      ULONG              MediaCharacteristics;
    } DiskInfo;
    struct {
      LARGE_INTEGER      Cylinders;
      STORAGE_MEDIA_TYPE MediaType;
      ULONG              TracksPerCylinder;
      ULONG              SectorsPerTrack;
      ULONG              BytesPerSector;
      ULONG              NumberMediaSides;
      ULONG              MediaCharacteristics;
    } RemovableDiskInfo;
    struct {
      STORAGE_MEDIA_TYPE MediaType;
      ULONG              MediaCharacteristics;
      ULONG              CurrentBlockSize;
      STORAGE_BUS_TYPE   BusType;
      union {
        struct {
          UCHAR MediumType;
          UCHAR DensityCode;
        } ScsiInformation;
      } BusSpecificData;
    } TapeInfo;
  } DeviceSpecific;
} DEVICE_MEDIA_INFO, *PDEVICE_MEDIA_INFO;
````


## -struct-fields

### -field DeviceSpecific


### -field DiskInfo

Describes a nonremovable (fixed) disk.


### -field Cylinders

Specifies the number of cylinders on this disk. 


### -field MediaType

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562216">MEDIA_TYPE</a> of <b>FixedMedia</b>. 


### -field TracksPerCylinder

Specifies the number of tracks per cylinder.


### -field SectorsPerTrack

Specifies the number of sectors per track.


### -field BytesPerSector

Specifies the number of bytes per sector.


### -field NumberMediaSides

Specifies the number of sides of the disk that can contain data: either 1 for one-sided media or 2 for two-sided media.


### -field MediaCharacteristics

<dl><a id="MEDIA_CURRENTLY_MOUNTED_"></a><a id="media_currently_mounted_"></a>
### -field MEDIA_CURRENTLY_MOUNTED
### -field MEDIA_ERASEABLE
### -field MEDIA_READ_ONLY
### -field MEDIA_READ_WRITE
### -field MEDIA_WRITE_ONCE
### -field MEDIA_WRITE_PROTECTED
</b>
</dl>
</dd>
</dl>

### -field RemovableDiskInfo

Describes a removable (nonfixed) disk.


### -field Cylinders

Specifies the number of cylinders on this disk. 


### -field MediaType

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562216">MEDIA_TYPE</a> or <a href="..\ntddstor\ne-ntddstor-_storage_media_type.md">STORAGE_MEDIA_TYPE</a> value that indicates the type of removable disk. 


### -field TracksPerCylinder

Specifies the number of tracks per cylinder.


### -field SectorsPerTrack

Specifies the number of sectors per track.


### -field BytesPerSector

Specifies the number of bytes per sector.


### -field NumberMediaSides

Specifies the number of sides of the disk that can contain data: 1 for one-sided media or 2 for two-sided media.


### -field MediaCharacteristics

Specifies characteristics of the disk, indicated by MEDIA_<i>XXX</i> flags ORed together. For a list of these flags, see the <b>DeviceSpecific.DiskInfo.MediaCharacteristics</b> member of the <b>DeviceSpecific.DiskInfo</b> structure.

</dd>
</dl>

### -field TapeInfo

Describes a tape.


### -field MediaType

Specifies a <a href="..\ntddstor\ne-ntddstor-_storage_media_type.md">STORAGE_MEDIA_TYPE</a> value that indicates the type of tape described in this structure. 


### -field MediaCharacteristics

Specifies characteristics of the tape, indicated by MEDIA_<i>XXX</i> flags ORed together. For a list of these flags, see the <b>DeviceSpecific.DiskInfo.MediaCharacteristics</b> member of the <b>DeviceSpecific.DiskInfo</b> structure.


### -field CurrentBlockSize

Specifies the current block size, in bytes.


### -field BusType

Specifies a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff566356">STORAGE_BUS_TYPE</a> that indicates the bus type.


### -field BusSpecificData


### -field ScsiInformation

Specifies bus-specific information from mode page data that describes the medium supported by the tape drive. Values for other bus types will be supplied in a later release.


### -field MediumType

Specifies the SCSI-specific medium type.


### -field DensityCode

Specifies the SCSI-specific current operating density for read/write operations.

</dd>
</dl>
</dd>
</dl>
</dd>
</dl>
</dd>
</dl>

## -remarks
This structure is used by a storage driver to indicate the types of media supported by a device and which type is currently mounted, if any. A driver must provide this information if it might control drives in a media library or changer or if its device might be accessed by the Removable Storage Manager (RSM). 

The driver fills in an array of <b>DEVICE_MEDIA_INFO</b> structures, one for each medium type supported by the device, embedded in a <a href="..\ntddstor\ns-ntddstor-_get_media_types.md">GET_MEDIA_TYPES</a> structure.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567939">TapeMiniGetMediaTypes</a>
</dt>
<dt>
<a href="..\ntddstor\ne-ntddstor-_storage_media_type.md">STORAGE_MEDIA_TYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DEVICE_MEDIA_INFO structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

