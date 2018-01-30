---
UID: NS:ntddstor._STORAGE_MEDIUM_PRODUCT_TYPE_DESCRIPTOR
title: "_STORAGE_MEDIUM_PRODUCT_TYPE_DESCRIPTOR"
author: windows-driver-content
description: Used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to describe the product type of a storage device.
old-location: storage\storage_medium_product_type_descriptor.htm
old-project: storage
ms.assetid: AC0C09DF-EFD4-457B-8ABC-C60890D3AF6A
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ntddstor/PSTORAGE_MEDIUM_PRODUCT_TYPE_DESCRIPTOR, storage.storage_medium_product_type_descriptor, ntddstor/STORAGE_MEDIUM_PRODUCT_TYPE_DESCRIPTOR, PSTORAGE_MEDIUM_PRODUCT_TYPE_DESCRIPTOR structure pointer [Storage Devices], _STORAGE_MEDIUM_PRODUCT_TYPE_DESCRIPTOR, STORAGE_MEDIUM_PRODUCT_TYPE_DESCRIPTOR structure [Storage Devices], PSTORAGE_MEDIUM_PRODUCT_TYPE_DESCRIPTOR, STORAGE_MEDIUM_PRODUCT_TYPE_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	STORAGE_MEDIUM_PRODUCT_TYPE_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: PSTORAGE_MEDIUM_PRODUCT_TYPE_DESCRIPTOR, STORAGE_MEDIUM_PRODUCT_TYPE_DESCRIPTOR
---

# _STORAGE_MEDIUM_PRODUCT_TYPE_DESCRIPTOR structure


## -description


Used in conjunction with the <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> request to describe the product type of a storage device.


## -syntax


````
typedef struct _STORAGE_MEDIUM_PRODUCT_TYPE_DESCRIPTOR {
  ULONG Version;
  ULONG Size;
  ULONG MediumProductType;
} STORAGE_MEDIUM_PRODUCT_TYPE_DESCRIPTOR, *PSTORAGE_MEDIUM_PRODUCT_TYPE_DESCRIPTOR;
````


## -struct-fields




### -field Version

Contains the size of this structure, in bytes, as defined by <code>Sizeof(STORAGE_MEDIUM_PRODUCT_TYPE_DESCRIPTOR)</code>. The value of this member will change as members are added to 
      the structure. 


### -field Size

Specifies the total size of the data returned, in bytes. This may include data that follows this 
      structure.


### -field MediumProductType

Specifies the product type of the storage device.
<table>
<tr>
<th><b>MediumProductType</b> value</th>
<th>Description</th>
</tr>
<tr>
<td><code>00h</code></td>
<td>Not indicated</td>
</tr>
<tr>
<td><code>01h</code></td>
<td>CFast</td>
</tr>
<tr>
<td><code>02h</code></td>
<td>CompactFlash</td>
</tr>
<tr>
<td><code>03h</code></td>
<td>Memory Stick</td>
</tr>
<tr>
<td><code>04h</code></td>
<td>MultiMediaCard</td>
</tr>
<tr>
<td><code>05h</code></td>
<td>Secure Digital Card (SD Card)</td>
</tr>
<tr>
<td><code>06h</code></td>
<td>QXD</td>
</tr>
<tr>
<td><code>07h</code></td>
<td>Universal Flash Storage</td>
</tr>
<tr>
<td><code>08h</code> to <code>EFh</code></td>
<td>Reserved</td>
</tr>
<tr>
<td><code>F0h</code> to <code>FFh</code></td>
<td>Vendor-specific</td>
</tr>
</table> 


## -see-also

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_MEDIUM_PRODUCT_TYPE_DESCRIPTOR structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

