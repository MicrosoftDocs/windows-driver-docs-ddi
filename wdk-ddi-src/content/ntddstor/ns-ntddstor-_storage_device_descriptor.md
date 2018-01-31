---
UID: NS:ntddstor._STORAGE_DEVICE_DESCRIPTOR
title: "_STORAGE_DEVICE_DESCRIPTOR"
author: windows-driver-content
description: The STORAGE_DEVICE_DESCRIPTOR structure is used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to retrieve the storage device descriptor data for a device.
old-location: storage\storage_device_descriptor.htm
old-project: storage
ms.assetid: 99b270a0-0634-41a8-9de7-d2a2d4c3059f
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ntddstor/PSTORAGE_DEVICE_DESCRIPTOR, STORAGE_DEVICE_DESCRIPTOR, _STORAGE_DEVICE_DESCRIPTOR, ntddstor/STORAGE_DEVICE_DESCRIPTOR, PSTORAGE_DEVICE_DESCRIPTOR structure pointer [Storage Devices], structs-general_3c393126-f5c8-47d8-bfb5-6127ce656e9a.xml, storage.storage_device_descriptor, STORAGE_DEVICE_DESCRIPTOR structure [Storage Devices], PSTORAGE_DEVICE_DESCRIPTOR
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddstor.h
apiname:
-	STORAGE_DEVICE_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: STORAGE_DEVICE_DESCRIPTOR, PSTORAGE_DEVICE_DESCRIPTOR
---

# _STORAGE_DEVICE_DESCRIPTOR structure


## -description


The <b>STORAGE_DEVICE_DESCRIPTOR</b> structure 
   is used in conjunction with the 
   <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> request to 
   retrieve the storage device descriptor data for a device.


## -syntax


````
typedef struct _STORAGE_DEVICE_DESCRIPTOR {
  ULONG            Version;
  ULONG            Size;
  UCHAR            DeviceType;
  UCHAR            DeviceTypeModifier;
  BOOLEAN          RemovableMedia;
  BOOLEAN          CommandQueueing;
  ULONG            VendorIdOffset;
  ULONG            ProductIdOffset;
  ULONG            ProductRevisionOffset;
  ULONG            SerialNumberOffset;
  STORAGE_BUS_TYPE BusType;
  ULONG            RawPropertiesLength;
  UCHAR            RawDeviceProperties[1];
} STORAGE_DEVICE_DESCRIPTOR, *PSTORAGE_DEVICE_DESCRIPTOR;
````


## -struct-fields




#### - Version

Indicates the size of the 
      <b>STORAGE_DEVICE_DESCRIPTOR</b> structure. The 
      value of this member will change as members are added to the structure.


#### - Size

Specifies the total size of the descriptor in bytes, including ID strings which are appended to the 
      structure.


#### - DeviceType

Specifies the device type as defined by the Small Computer Systems Interface (SCSI) specification.


#### - DeviceTypeModifier

Specifies the device type modifier, if any, as defined by the SCSI specification. If no device type 
      modifier exists, this member is zero.


#### - RemovableMedia

Indicates when <b>TRUE</b> that the device's media (if any) is removable. If the device 
      has no media, this member should be ignored. When <b>FALSE</b> the device's media is not 
      removable.


#### - CommandQueueing

Indicates when <b>TRUE</b> that the device supports multiple outstanding commands (SCSI 
      tagged queuing or equivalent). When <b>FALSE</b>, the device does not support SCSI-tagged 
      queuing or the equivalent. The STORPORT driver is responsible for synchronizing the commands.


#### - VendorIdOffset

Specifies the byte offset from the beginning of the structure to a <b>NULL</b>-terminated ASCII string that 
      contains the device's vendor ID. If the device has no vendor ID, this member is zero.


#### - ProductIdOffset

Specifies the byte offset from the beginning of the structure to a <b>NULL</b>-terminated ASCII string that 
      contains the device's product ID. If the device has no product ID, this member is zero.


#### - ProductRevisionOffset

Specifies the byte offset from the beginning of the structure to a <b>NULL</b>-terminated ASCII string that 
      contains the device's product revision string. If the device has no product revision string, this member is 
      zero.


#### - SerialNumberOffset

Specifies the byte offset from the beginning of the structure to a <b>NULL</b>-terminated ASCII string that 
      contains the device's serial number. If the device has no serial number, this member is zero.


#### - BusType

Specifies an enumerator value of type 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff566356">STORAGE_BUS_TYPE</a> that indicates the type of bus to 
      which the device is connected. This should be used to interpret the raw device properties at the end of this 
      structure (if any).


#### - RawPropertiesLength

Indicates the number of bytes of bus-specific data that have been appended to this descriptor.


#### - RawDeviceProperties

Contains an array of length one that serves as a place holder for the first byte of the bus specific 
      property data.


## -remarks


Applications and storage class drivers issue a device-control request with the I/O control code 
     <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> to retrieve 
     this structure, which contains information about a target device. The structure can be retrieved only from an 
     FDO; attempting to retrieve device properties from an adapter causes an error.

An application or driver can determine the required buffer size by casting the retrieved 
     <b>STORAGE_DEVICE_DESCRIPTOR</b> structure to a 
     <a href="..\ntddstor\ns-ntddstor-_storage_descriptor_header.md">STORAGE_DESCRIPTOR_HEADER</a>, which contains 
     only <b>Version</b> and <b>Size</b>.



## -see-also

<a href="..\ntddstor\ns-ntddstor-_storage_device_id_descriptor.md">STORAGE_DEVICE_ID_DESCRIPTOR</a>

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a>

<a href="..\ntddstor\ns-ntddstor-_storage_descriptor_header.md">STORAGE_DESCRIPTOR_HEADER</a>

<a href="..\wdm\nf-wdm-iobuilddeviceiocontrolrequest.md">IoBuildDeviceIoControlRequest</a>

<a href="..\ntddstor\ns-ntddstor-_storage_adapter_descriptor.md">STORAGE_ADAPTER_DESCRIPTOR</a>

<a href="..\ntddstor\ns-ntddstor-_storage_device_descriptor.md">STORAGE_DEVICE_DESCRIPTOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_DEVICE_DESCRIPTOR structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

