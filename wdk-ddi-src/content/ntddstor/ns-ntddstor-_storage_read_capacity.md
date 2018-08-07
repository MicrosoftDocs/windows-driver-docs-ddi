---
UID: NS:ntddstor._STORAGE_READ_CAPACITY
title: "_STORAGE_READ_CAPACITY"
author: windows-driver-content
description: The STORAGE_READ_CAPACITY contains the disk read capacity information returned from a IOCTL_STORAGE_READ_CAPACITIY request.
old-location: storage\storage_read_capacity.htm
tech.root: storage
ms.assetid: 891F04C5-277B-4197-942E-68ED21019950
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PSTORAGE_READ_CAPACITY, PSTORAGE_READ_CAPACITY structure pointer [Storage Devices], STORAGE_READ_CAPACITY, STORAGE_READ_CAPACITY structure [Storage Devices], _STORAGE_READ_CAPACITY, ntddstor/PSTORAGE_READ_CAPACITY, ntddstor/STORAGE_READ_CAPACITY, storage.storage_read_capacity
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
-	Ntddstor.h
api_name:
-	STORAGE_READ_CAPACITY
product:
- Windows
targetos: Windows
req.typenames: STORAGE_READ_CAPACITY, PSTORAGE_READ_CAPACITY
---

# _STORAGE_READ_CAPACITY structure


## -description


The <b>STORAGE_READ_CAPACITY</b> contains the disk read capacity information returned from a <a href="https://msdn.microsoft.com/FC4CFD33-5632-400A-90E5-583C6D6DFFD9">IOCTL_STORAGE_READ_CAPACITIY</a> request. 


## -struct-fields




### -field Version

The version of this structure. Set to <b>sizeof</b>(STORAGE_READ_CAPACITY).


### -field Size

The size of this structure. Set to <b>sizeof</b>(STORAGE_READ_CAPACITY).


### -field BlockLength

The number of bytes per block on disk.


### -field NumberOfBlocks

The total number of blocks on the disk.


### -field DiskLength

The total disk size in bytes.


## -see-also




<a href="https://msdn.microsoft.com/FC4CFD33-5632-400A-90E5-583C6D6DFFD9">IOCTL_STORAGE_READ_CAPACITIY</a>
 

 

