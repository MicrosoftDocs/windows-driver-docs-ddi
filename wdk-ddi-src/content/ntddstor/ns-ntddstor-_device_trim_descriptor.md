---
UID: NS:ntddstor._DEVICE_TRIM_DESCRIPTOR
title: "_DEVICE_TRIM_DESCRIPTOR"
author: windows-driver-content
description: The DEVICE_TRIM_DESCRIPTOR structure is used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to retrieve the trim descriptor data for a device.
old-location: storage\device_trim_descriptor.htm
old-project: storage
ms.assetid: e36bca55-63d0-41ef-83b9-8f0cfd450323
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PDEVICE_TRIM_DESCRIPTOR, DEVICE_TRIM_DESCRIPTOR, DEVICE_TRIM_DESCRIPTOR structure [Storage Devices], PDEVICE_TRIM_DESCRIPTOR, PDEVICE_TRIM_DESCRIPTOR structure pointer [Storage Devices], _DEVICE_TRIM_DESCRIPTOR, ntddstor/DEVICE_TRIM_DESCRIPTOR, ntddstor/PDEVICE_TRIM_DESCRIPTOR, storage.device_trim_descriptor, structs-general_eeaa452e-bc49-47ac-9d6f-4a7bbc022b2f.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddstor.h
api_name:
-	DEVICE_TRIM_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: DEVICE_TRIM_DESCRIPTOR, *PDEVICE_TRIM_DESCRIPTOR
---

# _DEVICE_TRIM_DESCRIPTOR structure


## -description


The DEVICE_TRIM_DESCRIPTOR structure is used in conjunction with the <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> request to retrieve the trim descriptor data for a device.


## -syntax


````
typedef struct _DEVICE_TRIM_DESCRIPTOR {
  ULONG   Version;
  ULONG   Size;
  BOOLEAN TrimEnabled;
} DEVICE_TRIM_DESCRIPTOR, *PDEVICE_TRIM_DESCRIPTOR;
````


## -struct-fields




### -field Version

Contains the size of the structure DEVICE_TRIM_DESCRIPTOR. The value of this member will change as members are added to the structure.


### -field Size

Specifies the total size of the descriptor, in bytes.


### -field TrimEnabled

Specifies whether trim is enabled for the device.


## -remarks



Storage class drivers issue a device-control request with the I/O control code  <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> to retrieve this structure, which contains trim information for the device. The structure can be retrieved either from the device object for the bus or from an FDO, which forwards the request to the underlying bus.




## -see-also

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DEVICE_TRIM_DESCRIPTOR structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

