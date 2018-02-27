---
UID: NS:ntddstor._STORAGE_DESCRIPTOR_HEADER
title: "_STORAGE_DESCRIPTOR_HEADER"
author: windows-driver-content
description: The STORAGE_DESCRIPTOR_HEADER structure is used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to retrieve the properties of a storage device or adapter.
old-location: storage\storage_descriptor_header.htm
old-project: storage
ms.assetid: 57d019b0-7914-42f6-a888-16042aa97444
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PSTORAGE_DESCRIPTOR_HEADER, PSTORAGE_DESCRIPTOR_HEADER structure pointer [Storage Devices], STORAGE_DESCRIPTOR_HEADER, STORAGE_DESCRIPTOR_HEADER structure [Storage Devices], _STORAGE_DESCRIPTOR_HEADER, ntddstor/PSTORAGE_DESCRIPTOR_HEADER, ntddstor/STORAGE_DESCRIPTOR_HEADER, storage.storage_descriptor_header, structs-general_9ba3bf25-17dc-41e1-9b3e-971d2ddd4780.xml
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
-	STORAGE_DESCRIPTOR_HEADER
product: Windows
targetos: Windows
req.typenames: STORAGE_DESCRIPTOR_HEADER, PSTORAGE_DESCRIPTOR_HEADER
---

# _STORAGE_DESCRIPTOR_HEADER structure


## -description


The STORAGE_DESCRIPTOR_HEADER structure is used in conjunction with the <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> request to retrieve the properties of a storage device or adapter. 


## -syntax


````
typedef struct _STORAGE_DESCRIPTOR_HEADER {
  ULONG Version;
  ULONG Size;
} STORAGE_DESCRIPTOR_HEADER, *PSTORAGE_DESCRIPTOR_HEADER;
````


## -struct-fields




### -field Version

Contains the version of the data reported. 


### -field Size

Indicates the quantity of data reported, in bytes. 


## -remarks



The data retrieved by IOCTL_STORAGE_QUERY_PROPERTY is reported in the buffer immediately following this structure. 

The IOCTL_STORAGE_QUERY_PROPERTY request reports one of three types of properties: a device descriptor, an adapter descriptor, or a set of device IDs taken from the device's SCSI vital product data pages. Device descriptors are reported in a structure of type <a href="..\ntddstor\ns-ntddstor-_storage_device_descriptor.md">STORAGE_DEVICE_DESCRIPTOR</a>. Adapter descriptors are reported in a structure of type <a href="..\ntddstor\ns-ntddstor-_storage_adapter_descriptor.md">STORAGE_ADAPTER_DESCRIPTOR</a>. Vital product page device IDs are reported in a structure of type <a href="..\ntddstor\ns-ntddstor-_storage_device_id_descriptor.md">STORAGE_DEVICE_ID_DESCRIPTOR</a>. 




## -see-also

<a href="..\ntddstor\ns-ntddstor-_storage_property_query.md">STORAGE_PROPERTY_QUERY</a>



<a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_DESCRIPTOR_HEADER structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

