---
UID: NS:ntddstor._STORAGE_DEVICE_DESCRIPTOR
title: _STORAGE_DEVICE_DESCRIPTOR (ntddstor.h)
description: The STORAGE_DEVICE_DESCRIPTOR structure is used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to retrieve the storage device descriptor data for a device.
old-location: storage\storage_device_descriptor.htm
tech.root: storage
ms.assetid: 99b270a0-0634-41a8-9de7-d2a2d4c3059f
ms.date: 03/29/2018
keywords: ["STORAGE_DEVICE_DESCRIPTOR structure"]
ms.keywords: PSTORAGE_DEVICE_DESCRIPTOR, PSTORAGE_DEVICE_DESCRIPTOR structure pointer [Storage Devices], STORAGE_DEVICE_DESCRIPTOR, STORAGE_DEVICE_DESCRIPTOR structure [Storage Devices], _STORAGE_DEVICE_DESCRIPTOR, ntddstor/PSTORAGE_DEVICE_DESCRIPTOR, ntddstor/STORAGE_DEVICE_DESCRIPTOR, storage.storage_device_descriptor, structs-general_3c393126-f5c8-47d8-bfb5-6127ce656e9a.xml
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
req.typenames: STORAGE_DEVICE_DESCRIPTOR, PSTORAGE_DEVICE_DESCRIPTOR
f1_keywords:
 - _STORAGE_DEVICE_DESCRIPTOR
 - ntddstor/_STORAGE_DEVICE_DESCRIPTOR
 - PSTORAGE_DEVICE_DESCRIPTOR
 - ntddstor/PSTORAGE_DEVICE_DESCRIPTOR
 - STORAGE_DEVICE_DESCRIPTOR
 - ntddstor/STORAGE_DEVICE_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - STORAGE_DEVICE_DESCRIPTOR
---

# _STORAGE_DEVICE_DESCRIPTOR structure


## -description

The <b>STORAGE_DEVICE_DESCRIPTOR</b> structure 
   is used in conjunction with the 
   <a href="/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a> request to 
   retrieve the storage device descriptor data for a device.

## -struct-fields

### -field Version

Indicates the size of the 
      <b>STORAGE_DEVICE_DESCRIPTOR</b> structure. The 
      value of this member will change as members are added to the structure.

### -field Size

Specifies the total size of the descriptor in bytes, including ID strings which are appended to the 
      structure.

### -field DeviceType

Specifies the device type as defined by the Small Computer Systems Interface (SCSI) specification.

### -field DeviceTypeModifier

Specifies the device type modifier, if any, as defined by the SCSI specification. If no device type 
      modifier exists, this member is zero.

### -field RemovableMedia

Indicates when <b>TRUE</b> that the device's media (if any) is removable. If the device 
      has no media, this member should be ignored. When <b>FALSE</b> the device's media is not 
      removable.

### -field CommandQueueing

Indicates when <b>TRUE</b> that the device supports multiple outstanding commands (SCSI 
      tagged queuing or equivalent). When <b>FALSE</b>, the device does not support SCSI-tagged 
      queuing or the equivalent. The STORPORT driver is responsible for synchronizing the commands.

### -field VendorIdOffset

Specifies the byte offset from the beginning of the structure to a <b>NULL</b>-terminated ASCII string that 
      contains the device's vendor ID. If the device has no vendor ID, this member is zero.

### -field ProductIdOffset

Specifies the byte offset from the beginning of the structure to a <b>NULL</b>-terminated ASCII string that 
      contains the device's product ID. If the device has no product ID, this member is zero.

### -field ProductRevisionOffset

Specifies the byte offset from the beginning of the structure to a <b>NULL</b>-terminated ASCII string that 
      contains the device's product revision string. If the device has no product revision string, this member is 
      zero.

### -field SerialNumberOffset

Specifies the byte offset from the beginning of the structure to a <b>NULL</b>-terminated ASCII string that 
      contains the device's serial number. If the device has no serial number, this member is zero.

### -field BusType

Specifies an enumerator value of type 
      <a href="/previous-versions/windows/hardware/drivers/ff566356(v=vs.85)">STORAGE_BUS_TYPE</a> that indicates the type of bus to 
      which the device is connected. This should be used to interpret the raw device properties at the end of this 
      structure (if any).

### -field RawPropertiesLength

Indicates the number of bytes of bus-specific data that have been appended to this descriptor.

### -field RawDeviceProperties

Contains an array of length one that serves as a place holder for the first byte of the bus specific 
      property data.

## -remarks

Applications and storage class drivers issue a device-control request with the I/O control code 
     <a href="/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a> to retrieve 
     this structure, which contains information about a target device. The structure can be retrieved only from an 
     FDO; attempting to retrieve device properties from an adapter causes an error.

An application or driver can determine the required buffer size by casting the retrieved 
     <b>STORAGE_DEVICE_DESCRIPTOR</b> structure to a 
     <a href="/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_descriptor_header">STORAGE_DESCRIPTOR_HEADER</a>, which contains 
     only <b>Version</b> and <b>Size</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuilddeviceiocontrolrequest">IoBuildDeviceIoControlRequest</a>



<a href="/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_adapter_descriptor">STORAGE_ADAPTER_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_descriptor_header">STORAGE_DESCRIPTOR_HEADER</a>



<a href="/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_device_descriptor">STORAGE_DEVICE_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_device_id_descriptor">STORAGE_DEVICE_ID_DESCRIPTOR</a>