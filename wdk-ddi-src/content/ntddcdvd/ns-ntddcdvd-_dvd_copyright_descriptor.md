---
UID: NS:ntddcdvd._DVD_COPYRIGHT_DESCRIPTOR
title: _DVD_COPYRIGHT_DESCRIPTOR (ntddcdvd.h)
description: The DVD_COPYRIGHT_DESCRIPTOR structure is used in conjunction with the IOCTL_DVD_READ_STRUCTURE request to retrieve a DVD copyright descriptor.
old-location: storage\dvd_copyright_descriptor.htm
tech.root: storage
ms.assetid: e3478867-394b-466c-ad9a-259bedd66669
ms.date: 03/29/2018
keywords: ["DVD_COPYRIGHT_DESCRIPTOR structure"]
ms.keywords: "*PDVD_COPYRIGHT_DESCRIPTOR, DVD_COPYRIGHT_DESCRIPTOR, DVD_COPYRIGHT_DESCRIPTOR structure [Storage Devices], PDVD_COPYRIGHT_DESCRIPTOR, PDVD_COPYRIGHT_DESCRIPTOR structure pointer [Storage Devices], _DVD_COPYRIGHT_DESCRIPTOR, ntddcdvd/DVD_COPYRIGHT_DESCRIPTOR, ntddcdvd/PDVD_COPYRIGHT_DESCRIPTOR, storage.dvd_copyright_descriptor, structs-DVD_35ca576a-d7b4-49df-95cf-1d5339c6ae78.xml"
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
targetos: Windows
req.typenames: DVD_COPYRIGHT_DESCRIPTOR, *PDVD_COPYRIGHT_DESCRIPTOR
f1_keywords:
 - _DVD_COPYRIGHT_DESCRIPTOR
 - ntddcdvd/_DVD_COPYRIGHT_DESCRIPTOR
 - PDVD_COPYRIGHT_DESCRIPTOR
 - ntddcdvd/PDVD_COPYRIGHT_DESCRIPTOR
 - DVD_COPYRIGHT_DESCRIPTOR
 - ntddcdvd/DVD_COPYRIGHT_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddcdvd.h
api_name:
 - DVD_COPYRIGHT_DESCRIPTOR
---

# _DVD_COPYRIGHT_DESCRIPTOR structure


## -description

The DVD_COPYRIGHT_DESCRIPTOR structure is used in conjunction with the <a href="/windows-hardware/drivers/ddi/ntddcdvd/ni-ntddcdvd-ioctl_dvd_read_structure">IOCTL_DVD_READ_STRUCTURE</a> request to retrieve a DVD copyright descriptor.

## -struct-fields

### -field CopyrightProtectionType

Indicates, when set to 1, the presence of data specific to a copyright protection system. A value of zero indicates there is no such data. All other values are reserved.

### -field RegionManagementInformation

Indicates in which regions of the world the disc can be played. Each bit represents one of eight regions. If a bit is set, the disc cannot be played in the corresponding region. If a bit is not set, the disc can be played in the corresponding region.

### -field Reserved

Reserved.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddcdvd/ni-ntddcdvd-ioctl_dvd_read_structure">IOCTL_DVD_READ_STRUCTURE</a>