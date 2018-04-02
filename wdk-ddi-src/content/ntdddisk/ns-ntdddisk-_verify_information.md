---
UID: NS:ntdddisk._VERIFY_INFORMATION
title: "_VERIFY_INFORMATION"
author: windows-driver-content
description: The VERIFY_INFORMATION structure provides information used to verify the existence of a disk extent.
old-location: storage\verify_information.htm
old-project: storage
ms.assetid: 7bb5c2ff-9bdb-4958-b290-9edb18d02668
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PVERIFY_INFORMATION, PVERIFY_INFORMATION, PVERIFY_INFORMATION structure pointer [Storage Devices], VERIFY_INFORMATION, VERIFY_INFORMATION structure [Storage Devices], _VERIFY_INFORMATION, ntdddisk/PVERIFY_INFORMATION, ntdddisk/VERIFY_INFORMATION, storage.verify_information, structs-disk_fbed0038-effc-40d8-8814-921dfd627a94.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
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
-	ntdddisk.h
api_name:
-	VERIFY_INFORMATION
product: Windows
targetos: Windows
req.typenames: VERIFY_INFORMATION, *PVERIFY_INFORMATION
---

# _VERIFY_INFORMATION structure


## -description


The VERIFY_INFORMATION structure provides information used to verify the existence of a disk extent.  


## -struct-fields




### -field StartingOffset

Specifies the starting offset, in bytes, of the disk extent. 


### -field Length

Indicates the length, in bytes, of the disk extent. 


## -remarks



VERIFY_INFORMATION is the output buffer for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560420">IOCTL_DISK_VERIFY</a> control code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560420">IOCTL_DISK_VERIFY</a>
 

 

