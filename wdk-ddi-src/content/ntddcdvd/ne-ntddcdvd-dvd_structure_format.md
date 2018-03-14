---
UID: NE:ntddcdvd.DVD_STRUCTURE_FORMAT
title: DVD_STRUCTURE_FORMAT
author: windows-driver-content
description: The DVD_STRUCTURE_FORMAT enumeration type is used in conjunction with the IOCTL_DVD_READ_STRUCTURE request and the DVD_READ_STRUCTURE structure to retrieve a DVD descriptor.
old-location: storage\dvd_structure_format.htm
old-project: storage
ms.assetid: 0f3ca59b-f7e9-4bd7-a652-f7f0a6075d80
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDVD_STRUCTURE_FORMAT, DVD_STRUCTURE_FORMAT, DVD_STRUCTURE_FORMAT enumeration [Storage Devices], DvdBCADescriptor, DvdCopyrightDescriptor, DvdDiskKeyDescriptor, DvdManufacturerDescriptor, DvdMaxDescriptor, DvdPhysicalDescriptor, PDVD_STRUCTURE_FORMAT, PDVD_STRUCTURE_FORMAT enumeration pointer [Storage Devices], ntddcdvd/DVD_STRUCTURE_FORMAT, ntddcdvd/DvdBCADescriptor, ntddcdvd/DvdCopyrightDescriptor, ntddcdvd/DvdDiskKeyDescriptor, ntddcdvd/DvdManufacturerDescriptor, ntddcdvd/DvdMaxDescriptor, ntddcdvd/DvdPhysicalDescriptor, ntddcdvd/PDVD_STRUCTURE_FORMAT, storage.dvd_structure_format, structs-DVD_299fec4b-1ed0-43ea-a522-716c1a585d0e.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
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
-	ntddcdvd.h
api_name:
-	DVD_STRUCTURE_FORMAT
product: Windows
targetos: Windows
req.typenames: DVD_STRUCTURE_FORMAT, *PDVD_STRUCTURE_FORMAT
---

# DVD_STRUCTURE_FORMAT enumeration


## -description


The DVD_STRUCTURE_FORMAT enumeration type is used in conjunction with the <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_dvd_read_structure.md">IOCTL_DVD_READ_STRUCTURE</a> request and the <a href="..\ntddcdvd\ns-ntddcdvd-dvd_read_structure.md">DVD_READ_STRUCTURE</a> structure to retrieve a DVD descriptor.


## -syntax


````
typedef enum DVD_STRUCTURE_FORMAT { 
  DvdPhysicalDescriptor      = 0,
  DvdCopyrightDescriptor     = 1,
  DvdDiskKeyDescriptor       = 2,
  DvdBCADescriptor           = 3,
  DvdManufacturerDescriptor  = 4,
  DvdMaxDescriptor           = 5
} DVD_STRUCTURE_FORMAT, *PDVD_STRUCTURE_FORMAT;
````


## -enum-fields




### -field DvdPhysicalDescriptor

Indicates that caller is requesting a DVD physical descriptor. 


### -field DvdCopyrightDescriptor

Indicates that caller is requesting a DVD copyright descriptor containing copyright information from the DVD lead-in area. 


### -field DvdDiskKeyDescriptor

Indicates that caller is requesting a DVD key descriptor containing the disc key obfuscated using the bus key. 


### -field DvdBCADescriptor

Indicates that caller is requesting a DVD burst cutting area (BCA) descriptor. 


### -field DvdManufacturerDescriptor

Indicates that caller is requesting a DVD manufacturer descriptor containing disc manufacturing information from the DVD lead-in area. 


### -field DvdMaxDescriptor

Indicates that caller is requesting a DVD max descriptor. 


## -see-also

<a href="..\ntddcdvd\ns-ntddcdvd-dvd_read_structure.md">DVD_READ_STRUCTURE</a>



<a href="..\ntddcdvd\ni-ntddcdvd-ioctl_dvd_read_structure.md">IOCTL_DVD_READ_STRUCTURE</a>



 

 


