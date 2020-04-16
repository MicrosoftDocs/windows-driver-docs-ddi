---
UID: NS:fltuserstructures._FILTER_VOLUME_BASIC_INFORMATION
title: _FILTER_VOLUME_BASIC_INFORMATION (fltuserstructures.h)
description: The caller-allocated FILTER_VOLUME_BASIC_INFORMATION structure contains basic information for a volume.
old-location: ifsk\filter_volume_basic_information.htm
tech.root: ifsk
ms.assetid: f6b5ccc2-81d6-47be-94dd-cf92842de51c
ms.date: 04/16/2018
keywords: ["_FILTER_VOLUME_BASIC_INFORMATION structure"]
ms.keywords: "*PFILTER_VOLUME_BASIC_INFORMATION, FILTER_VOLUME_BASIC_INFORMATION, FILTER_VOLUME_BASIC_INFORMATION structure [Installable File System Drivers], FltSystemStructures_7bc0a3dc-37e1-4783-aecd-f4ef96e38a32.xml, PFILTER_VOLUME_BASIC_INFORMATION, PFILTER_VOLUME_BASIC_INFORMATION structure pointer [Installable File System Drivers], _FILTER_VOLUME_BASIC_INFORMATION, fltuserstructures/FILTER_VOLUME_BASIC_INFORMATION, fltuserstructures/PFILTER_VOLUME_BASIC_INFORMATION, ifsk.filter_volume_basic_information"
f1_keywords:
 - "fltuserstructures/FILTER_VOLUME_BASIC_INFORMATION"
req.header: fltuserstructures.h
req.include-header: FltUser.h, FltKernel.h
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
- fltuserstructures.h
api_name:
- FILTER_VOLUME_BASIC_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: FILTER_VOLUME_BASIC_INFORMATION, *PFILTER_VOLUME_BASIC_INFORMATION
---

# _FILTER_VOLUME_BASIC_INFORMATION structure


## -description


The caller-allocated FILTER_VOLUME_BASIC_INFORMATION  structure contains basic information for a volume.


## -struct-fields




### -field FilterVolumeNameLength

Read-only length, in bytes, of the volume name.


### -field FilterVolumeName

Read-only name of the volume of <b>FilterVolumeNameLength</b> length.  This Unicode string is not NULL-terminated. 


## -remarks



Filter manager enumeration routines, such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumeratevolumeinformation">FltEnumerateVolumeInformation</a>, can fill a buffer with structures of type FILTER_VOLUME_BASIC_INFORMATION where each structure represents a volume known to filter manager.  This list of structures can contain multiple volumes with the same name.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/understanding-volume-enumerations-with-duplicate-volume-names">Understanding Volume Enumerations with Duplicate Volume Names</a>.

The FILTER_VOLUME_BASIC_INFORMATION structure must be aligned on a LONGLONG (8-byte) boundary. If a buffer contains two or more of these structures, the <b>NextEntryOffset</b> value in each structure falls on an 8-byte boundary.

A FILTER_VOLUME_BASIC_INFORMATION structure can be allocated from paged or nonpaged pool.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltuserstructures/ns-fltuserstructures-_filter_volume_standard_information">FILTER_VOLUME_STANDARD_INFORMATION</a>



<a href="https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filtervolumefindclose">FilterVolumeFindClose</a>



<a href="https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filtervolumefindfirst">FilterVolumeFindFirst</a>



<a href="https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filtervolumefindnext">FilterVolumeFindNext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumeratevolumeinformation">FltEnumerateVolumeInformation</a>
 

 

