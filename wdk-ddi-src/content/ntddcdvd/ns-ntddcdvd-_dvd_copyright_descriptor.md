---
UID: NS:ntddcdvd._DVD_COPYRIGHT_DESCRIPTOR
title: "_DVD_COPYRIGHT_DESCRIPTOR"
author: windows-driver-content
description: The DVD_COPYRIGHT_DESCRIPTOR structure is used in conjunction with the IOCTL_DVD_READ_STRUCTURE request to retrieve a DVD copyright descriptor.
old-location: storage\dvd_copyright_descriptor.htm
old-project: storage
ms.assetid: e3478867-394b-466c-ad9a-259bedd66669
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ntddcdvd/PDVD_COPYRIGHT_DESCRIPTOR, ntddcdvd/DVD_COPYRIGHT_DESCRIPTOR, DVD_COPYRIGHT_DESCRIPTOR, storage.dvd_copyright_descriptor, PDVD_COPYRIGHT_DESCRIPTOR, structs-DVD_35ca576a-d7b4-49df-95cf-1d5339c6ae78.xml, *PDVD_COPYRIGHT_DESCRIPTOR, PDVD_COPYRIGHT_DESCRIPTOR structure pointer [Storage Devices], _DVD_COPYRIGHT_DESCRIPTOR, DVD_COPYRIGHT_DESCRIPTOR structure [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddcdvd.h
apiname:
-	DVD_COPYRIGHT_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: "*PDVD_COPYRIGHT_DESCRIPTOR, DVD_COPYRIGHT_DESCRIPTOR"
---

# _DVD_COPYRIGHT_DESCRIPTOR structure


## -description


The DVD_COPYRIGHT_DESCRIPTOR structure is used in conjunction with the <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_dvd_read_structure.md">IOCTL_DVD_READ_STRUCTURE</a> request to retrieve a DVD copyright descriptor. 


## -syntax


````
typedef struct _DVD_COPYRIGHT_DESCRIPTOR {
  UCHAR  CopyrightProtectionType;
  UCHAR  RegionManagementInformation;
  USHORT Reserved;
} DVD_COPYRIGHT_DESCRIPTOR, *PDVD_COPYRIGHT_DESCRIPTOR;
````


## -struct-fields




### -field CopyrightProtectionType

Indicates, when set to 1, the presence of data specific to a copyright protection system. A value of zero indicates there is no such data. All other values are reserved.


### -field RegionManagementInformation

Indicates in which regions of the world the disc can be played. Each bit represents one of eight regions. If a bit is set, the disc cannot be played in the corresponding region. If a bit is not set, the disc can be played in the corresponding region. 


### -field Reserved

Reserved. 


## -see-also

<a href="..\ntddcdvd\ni-ntddcdvd-ioctl_dvd_read_structure.md">IOCTL_DVD_READ_STRUCTURE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DVD_COPYRIGHT_DESCRIPTOR structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

