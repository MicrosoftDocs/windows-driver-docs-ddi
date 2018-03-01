---
UID: NS:ntddstor._STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR
title: "_STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR"
author: windows-driver-content
description: The STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR structure is used to retrieve the attributes information for a device.
old-location: storage\storage_device_attributes_descriptor.htm
old-project: storage
ms.assetid: DA8434EF-6163-4D07-A81D-D1AC2D55BFB4
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PSTORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR, PSTORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR structure pointer [Storage Devices], STORAGE_ATTRIBUTE_ASYNC_EVENT_NOTIFICATION, STORAGE_ATTRIBUTE_BLOCK_IO, STORAGE_ATTRIBUTE_BYTE_ADDRESSABLE_IO, STORAGE_ATTRIBUTE_DYNAMIC_PERSISTENCE, STORAGE_ATTRIBUTE_PERF_SIZE_INDEPENDENT, STORAGE_ATTRIBUTE_VOLATILE, STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR, STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR structure [Storage Devices], _STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR, ntddstor/PSTORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR, ntddstor/STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR, storage.storage_device_attributes_descriptor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR, PSTORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR
---

# _STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR structure


## -description


The STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR structure is used to retrieve the attributes information for a  device.


## -syntax


````
typedef struct _STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR {
  ULONG   Version;
  ULONG   Size;
  ULONG64 Attributes;
} STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR, *PSTORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR;
````


## -struct-fields




### -field Version

Contains the version of the data reported. 


### -field Size

Indicates the quantity of data reported, in bytes. This is the <code>sizeof(STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR)</code>.


### -field Attributes

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="STORAGE_ATTRIBUTE_BYTE_ADDRESSABLE_IO"></a><a id="storage_attribute_byte_addressable_io"></a><dl>
<dt><b>STORAGE_ATTRIBUTE_BYTE_ADDRESSABLE_IO</b></dt>
<dt>0x01</dt>
</dl>
</td>
<td width="60%">
Attribute that indicates a storage device supports byte addressable IO.

</td>
</tr>
<tr>
<td width="40%"><a id="STORAGE_ATTRIBUTE_BLOCK_IO"></a><a id="storage_attribute_block_io"></a><dl>
<dt><b>STORAGE_ATTRIBUTE_BLOCK_IO</b></dt>
<dt>0x02</dt>
</dl>
</td>
<td width="60%">
Attribute that indicates a storage device supports block IO.

</td>
</tr>
<tr>
<td width="40%"><a id="STORAGE_ATTRIBUTE_DYNAMIC_PERSISTENCE"></a><a id="storage_attribute_dynamic_persistence"></a><dl>
<dt><b>STORAGE_ATTRIBUTE_DYNAMIC_PERSISTENCE</b></dt>
<dt>0x04</dt>
</dl>
</td>
<td width="60%">
Attribute that indicates that persistence of data on storage device may change.

</td>
</tr>
<tr>
<td width="40%"><a id="STORAGE_ATTRIBUTE_VOLATILE"></a><a id="storage_attribute_volatile"></a><dl>
<dt><b>STORAGE_ATTRIBUTE_VOLATILE</b></dt>
<dt>0x08</dt>
</dl>
</td>
<td width="60%">
Attribute that indicates a storage device is volatile and does not support persistence of data.

</td>
</tr>
<tr>
<td width="40%"><a id="STORAGE_ATTRIBUTE_ASYNC_EVENT_NOTIFICATION"></a><a id="storage_attribute_async_event_notification"></a><dl>
<dt><b>STORAGE_ATTRIBUTE_ASYNC_EVENT_NOTIFICATION</b></dt>
<dt>0x10</dt>
</dl>
</td>
<td width="60%">
Reserved

</td>
</tr>
<tr>
<td width="40%"><a id="STORAGE_ATTRIBUTE_PERF_SIZE_INDEPENDENT"></a><a id="storage_attribute_perf_size_independent"></a><dl>
<dt><b>STORAGE_ATTRIBUTE_PERF_SIZE_INDEPENDENT</b></dt>
<dt>0x20</dt>
</dl>
</td>
<td width="60%">
Attribute that indicates a storage device has IO performance independent of IO sizes.

</td>
</tr>
</table>
 

