---
UID: NS:ntddcdvd._DVD_REGION
title: _DVD_REGION (ntddcdvd.h)
description: The DVD_REGION structure is used in conjunction with the IOCTL_DVD_GET_REGION request to retrieve region playback control (RPC) information for a DVD device.
old-location: storage\dvd_region.htm
tech.root: storage
ms.assetid: a2e31a1a-59e4-4a83-b866-944ef1693f65
ms.date: 03/29/2018
ms.keywords: "*PDVD_REGION, DVD_REGION, DVD_REGION structure [Storage Devices], PDVD_REGION, PDVD_REGION structure pointer [Storage Devices], _DVD_REGION, ntddcdvd/DVD_REGION, ntddcdvd/PDVD_REGION, storage.dvd_region, structs-DVD_b1569a34-c55e-482b-b87e-30becd20e2c1.xml"
f1_keywords:
 - "ntddcdvd/DVD_REGION"
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
- DVD_REGION
product:
- Windows
targetos: Windows
req.typenames: DVD_REGION, *PDVD_REGION
---

# _DVD_REGION structure


## -description


The DVD_REGION structure is used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ni-ntddcdvd-ioctl_dvd_get_region">IOCTL_DVD_GET_REGION</a> request to retrieve region playback control (RPC) information for a DVD device.


## -struct-fields




### -field CopySystem

Indicates the copyright protection type. For more information about copyright protection types, see the <i>SCSI Multimedia Commands - 3</i> (MMC-3) specification.


### -field RegionData

Indicates the region code of the currently mounted DVD media. This is an eight-bit bitmask, with one bit for each DVD region. A value of 0x00 means that no region is specified. 


### -field SystemRegion

Indicates the region code of the DVD player. This is an eight-bit bitmask, with one bit for each system region. A value of 0x00 means that no region is specified. 


### -field ResetCount

Indicates the remaining number of times the DVD device's region code can be changed by the user. This member can hold a value between 0 and 7.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ni-ntddcdvd-ioctl_dvd_get_region">IOCTL_DVD_GET_REGION</a>
 

 

