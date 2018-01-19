---
UID: NS:ntddstor._STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR
title: _STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR
author: windows-driver-content
description: The STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR structure is used to retrieve the attributes information for a device.
old-location: storage\storage_device_attributes_descriptor.htm
old-project: storage
ms.assetid: DA8434EF-6163-4D07-A81D-D1AC2D55BFB4
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR, STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR, PSTORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR
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
req.alt-api: STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR
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

### -field STORAGE_ATTRIBUTE_BYTE_ADDRESSABLE_IO
### -field 0x01

</td>
<td width="60%">
Attribute that indicates a storage device supports byte addressable IO.

</td>
</tr>
<tr>

### -field STORAGE_ATTRIBUTE_BLOCK_IO
### -field 0x02

</td>
<td width="60%">
Attribute that indicates a storage device supports block IO.

</td>
</tr>
<tr>

### -field STORAGE_ATTRIBUTE_DYNAMIC_PERSISTENCE
### -field 0x04

</td>
<td width="60%">
Attribute that indicates that persistence of data on storage device may change.

</td>
</tr>
<tr>

### -field STORAGE_ATTRIBUTE_VOLATILE
### -field 0x08

</td>
<td width="60%">
Attribute that indicates a storage device is volatile and does not support persistence of data.

</td>
</tr>
<tr>

### -field STORAGE_ATTRIBUTE_ASYNC_EVENT_NOTIFICATION
### -field 0x10

</td>
<td width="60%">
Reserved

</td>
</tr>
<tr>

### -field STORAGE_ATTRIBUTE_PERF_SIZE_INDEPENDENT
### -field 0x20

</td>
<td width="60%">
Attribute that indicates a storage device has IO performance independent of IO sizes.

</td>
</tr>
</table>
 


## -remarks
