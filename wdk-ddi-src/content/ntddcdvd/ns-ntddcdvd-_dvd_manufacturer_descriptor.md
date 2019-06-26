---
UID: NS:ntddcdvd._DVD_MANUFACTURER_DESCRIPTOR
title: _DVD_MANUFACTURER_DESCRIPTOR (ntddcdvd.h)
description: The DVD_MANUFACTURER_DESCRIPTOR structure is used in conjunction with the IOCTL_DVD_READ_STRUCTURE request to retrieve a DVD manufacturer descriptor.
old-location: storage\dvd_manufacturer_descriptor.htm
tech.root: storage
ms.assetid: 19a65a8f-5272-424a-85b3-88074fb9e22f
ms.date: 03/29/2018
ms.keywords: "*PDVD_MANUFACTURER_DESCRIPTOR, DVD_MANUFACTURER_DESCRIPTOR, DVD_MANUFACTURER_DESCRIPTOR structure [Storage Devices], PDVD_MANUFACTURER_DESCRIPTOR, PDVD_MANUFACTURER_DESCRIPTOR structure pointer [Storage Devices], _DVD_MANUFACTURER_DESCRIPTOR, ntddcdvd/DVD_MANUFACTURER_DESCRIPTOR, ntddcdvd/PDVD_MANUFACTURER_DESCRIPTOR, storage.dvd_manufacturer_descriptor, structs-DVD_420be36e-90ef-459a-a3c8-4ecc233a0d82.xml"
ms.topic: struct
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddcdvd.h
api_name:
- DVD_MANUFACTURER_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: DVD_MANUFACTURER_DESCRIPTOR, *PDVD_MANUFACTURER_DESCRIPTOR
---

# _DVD_MANUFACTURER_DESCRIPTOR structure


## -description


The DVD_MANUFACTURER_DESCRIPTOR structure is used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdvd/ni-ntddcdvd-ioctl_dvd_read_structure">IOCTL_DVD_READ_STRUCTURE</a> request to retrieve a DVD manufacturer descriptor. 


## -struct-fields




### -field ManufacturingInformation

Contains an array holding the manufacturing information taken from the DVD media lead-in area. In the case of DVD-R multisession disc, this information is taken from the last border-in area.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdvd/ni-ntddcdvd-ioctl_dvd_read_structure">IOCTL_DVD_READ_STRUCTURE</a>
 

 

