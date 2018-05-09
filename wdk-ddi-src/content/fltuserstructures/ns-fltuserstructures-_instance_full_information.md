---
UID: NS:fltuserstructures._INSTANCE_FULL_INFORMATION
title: "_INSTANCE_FULL_INFORMATION"
author: windows-driver-content
description: The INSTANCE_FULL_INFORMATION structure contains full information for a minifilter instance.
old-location: ifsk\instance_full_information.htm
old-project: ifsk
ms.assetid: 6c034749-c110-4623-8a7b-a19235cad298
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltSystemStructures_db070365-3d91-4bbc-9c53-44c4b2974de0.xml, INSTANCE_FULL_INFORMATION, INSTANCE_FULL_INFORMATION structure [Installable File System Drivers], PINSTANCE_FULL_INFORMATION, PINSTANCE_FULL_INFORMATION structure pointer [Installable File System Drivers], _INSTANCE_FULL_INFORMATION, fltuserstructures/INSTANCE_FULL_INFORMATION, fltuserstructures/PINSTANCE_FULL_INFORMATION, ifsk.instance_full_information
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fltuserstructures.h
req.include-header: FltUserStructures.h, FltUser.h, FltKernel.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available starting with Microsoft Windows 2000 SP4 with Update Rollup, Windows XP SP2,  Microsoft Windows Server 2003 SP1, and Windows Vista or later versions of Windows operating systems,
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
-	fltuserstructures.h
api_name:
-	INSTANCE_FULL_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: INSTANCE_FULL_INFORMATION, PINSTANCE_FULL_INFORMATION
---

# _INSTANCE_FULL_INFORMATION structure


## -description


The INSTANCE_FULL_INFORMATION structure contains full information for a minifilter instance. 


## -struct-fields




### -field NextEntryOffset

A byte offset of the next INSTANCE_FULL_INFORMATION entry. If multiple entries are present in a buffer, the last entry contains a zero.  


### -field InstanceNameLength

The length, in bytes, of the instance name. 


### -field InstanceNameBufferOffset

A byte offset of the first character of the instance name string. This character is followed in memory by the remainder of the string. 


### -field AltitudeLength

The length, in bytes, of the altitude string. 


### -field AltitudeBufferOffset

A byte offset of the first character of the altitude string. This character is followed in memory by the remainder of the string. 


### -field VolumeNameLength

The length, in bytes, of the volume name. 


### -field VolumeNameBufferOffset

A byte offset of the first character of the volume name string. This character is followed in memory by the remainder of the string (for example, "\Device\HarddiskVolume1"). 


### -field FilterNameLength

The length, in bytes, of the minifilter name. 


### -field FilterNameBufferOffset

A byte offset of the first character of the minifilter name string. This character is followed in memory by the remainder of the string. 


## -remarks



This structure must be aligned on a LONGLONG (8-byte) boundary. If a buffer contains two or more of these structures, the <b>NextEntryOffset</b> value in each entry, except the last, falls on an 8-byte boundary.

The content of all character string buffers referenced by this structure are Unicode.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540448">FilterAttachAtAltitude</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540538">FilterInstanceFindClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540541">FilterInstanceFindFirst</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541493">FilterInstanceFindNext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541499">FilterInstanceGetInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541535">FilterVolumeInstanceFindClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541541">FilterVolumeInstanceFindFirst</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541551">FilterVolumeInstanceFindNext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548172">INSTANCE_AGGREGATE_STANDARD_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548176">INSTANCE_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548190">INSTANCE_PARTIAL_INFORMATION</a>
 

 

