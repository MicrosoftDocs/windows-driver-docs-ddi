---
UID: NS:fltuserstructures._INSTANCE_FULL_INFORMATION
title: _INSTANCE_FULL_INFORMATION
author: windows-driver-content
description: The INSTANCE_FULL_INFORMATION structure contains full information for a minifilter instance.
old-location: ifsk\instance_full_information.htm
old-project: ifsk
ms.assetid: 6c034749-c110-4623-8a7b-a19235cad298
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _INSTANCE_FULL_INFORMATION, PINSTANCE_FULL_INFORMATION, INSTANCE_FULL_INFORMATION
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
req.alt-api: INSTANCE_FULL_INFORMATION
req.alt-loc: fltuserstructures.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: PINSTANCE_FULL_INFORMATION, INSTANCE_FULL_INFORMATION
---

# _INSTANCE_FULL_INFORMATION structure



## -description
The INSTANCE_FULL_INFORMATION structure contains full information for a minifilter instance. 



## -syntax

````
typedef struct _INSTANCE_FULL_INFORMATION {
  ULONG  NextEntryOffset;
  USHORT InstanceNameLength;
  USHORT InstanceNameBufferOffset;
  USHORT AltitudeLength;
  USHORT AltitudeBufferOffset;
  USHORT VolumeNameLength;
  USHORT VolumeNameBufferOffset;
  USHORT FilterNameLength;
  USHORT FilterNameBufferOffset;
} INSTANCE_FULL_INFORMATION, *PINSTANCE_FULL_INFORMATION;
````


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
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540448">FilterAttachAtAltitude</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540538">FilterInstanceFindClose</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540541">FilterInstanceFindFirst</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541493">FilterInstanceFindNext</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541499">FilterInstanceGetInformation</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541535">FilterVolumeInstanceFindClose</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541541">FilterVolumeInstanceFindFirst</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541551">FilterVolumeInstanceFindNext</a>
</dt>
<dt>
<a href="..\fltuserstructures\ns-fltuserstructures-_instance_aggregate_standard_information.md">INSTANCE_AGGREGATE_STANDARD_INFORMATION</a>
</dt>
<dt>
<a href="..\fltuserstructures\ns-fltuserstructures-_instance_basic_information.md">INSTANCE_BASIC_INFORMATION</a>
</dt>
<dt>
<a href="..\fltuserstructures\ns-fltuserstructures-_instance_partial_information.md">INSTANCE_PARTIAL_INFORMATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20INSTANCE_FULL_INFORMATION structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

