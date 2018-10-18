---
UID: NS:ntddcdvd._DVD_BCA_DESCRIPTOR
title: "_DVD_BCA_DESCRIPTOR"
author: windows-driver-content
description: The DVD_BCA_DESCRIPTOR structure is used in conjunction with the IOCTL_DVD_READ_STRUCTURE request to retrieve a DVD burst cutting area (BCA) descriptor.
old-location: storage\dvd_bca_descriptor.htm
tech.root: storage
ms.assetid: a573beb8-7019-4605-ab37-5871f67c585d
ms.date: 03/29/2018
ms.keywords: "*PDVD_BCA_DESCRIPTOR, DVD_BCA_DESCRIPTOR, DVD_BCA_DESCRIPTOR structure [Storage Devices], PDVD_BCA_DESCRIPTOR, PDVD_BCA_DESCRIPTOR structure pointer [Storage Devices], _DVD_BCA_DESCRIPTOR, ntddcdvd/DVD_BCA_DESCRIPTOR, ntddcdvd/PDVD_BCA_DESCRIPTOR, storage.dvd_bca_descriptor, structs-DVD_4bbbd075-9b9f-40a6-b52d-e96b8ad7118b.xml"
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddcdvd.h
api_name:
-	DVD_BCA_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: DVD_BCA_DESCRIPTOR, *PDVD_BCA_DESCRIPTOR
---

# _DVD_BCA_DESCRIPTOR structure


## -description


The DVD_BCA_DESCRIPTOR structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560426">IOCTL_DVD_READ_STRUCTURE</a> request to retrieve a DVD burst cutting area (BCA) descriptor. 


## -struct-fields




### -field BCAInformation

Contains an array that holds vendor-defined information retrieved from the burst cutting area.


## -remarks



The contents of the BCA region are specified by the media manufacturer. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560426">IOCTL_DVD_READ_STRUCTURE</a>
 

 

