---
UID: NS:fltuserstructures._FILTER_FULL_INFORMATION
title: _FILTER_FULL_INFORMATION (fltuserstructures.h)
description: The FILTER_FULL_INFORMATION structure contains full information for a minifilter driver.
old-location: ifsk\filter_full_information.htm
tech.root: ifsk
ms.assetid: fb592350-76e2-4655-b6db-854fd48aa827
ms.date: 04/16/2018
keywords: ["_FILTER_FULL_INFORMATION structure"]
ms.keywords: "*PFILTER_FULL_INFORMATION, FILTER_FULL_INFORMATION, FILTER_FULL_INFORMATION structure [Installable File System Drivers], FltSystemStructures_e72c2545-4938-4a3e-b3c8-95fd7f46239a.xml, PFILTER_FULL_INFORMATION, PFILTER_FULL_INFORMATION structure pointer [Installable File System Drivers], _FILTER_FULL_INFORMATION, fltuserstructures/FILTER_FULL_INFORMATION, fltuserstructures/PFILTER_FULL_INFORMATION, ifsk.filter_full_information"
f1_keywords:
 - "fltuserstructures/FILTER_FULL_INFORMATION"
 - "FILTER_FULL_INFORMATION"
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
- FILTER_FULL_INFORMATION
targetos: Windows
req.typenames: FILTER_FULL_INFORMATION, *PFILTER_FULL_INFORMATION
---

# _FILTER_FULL_INFORMATION structure


## -description


The FILTER_FULL_INFORMATION structure contains full information for a minifilter driver. 


## -struct-fields




### -field NextEntryOffset

Byte offset of the next FILTER_FULL_INFORMATION entry, if multiple entries are present in a buffer. This member is zero if no other entries follow this one. 


### -field FrameID

Zero-based index of the current frame. 


### -field NumberOfInstances

Number of instances that currently exist for this minifilter. 


### -field FilterNameLength

Length, in bytes, of the minifilter name. 


### -field FilterNameBuffer

Specifies the first character of the filter name string. This character is followed in memory by the remainder of the string. The length of the string is specified by the <b>FilterNameLength</b> member. The string is Unicode and is not NULL-terminated. 


## -remarks



The FILTER_FULL_INFORMATION structure is passed as a parameter to routines such as <a href="https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filterfindfirst">FilterFindFirst</a>, <a href="https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filterfindnext">FilterFindNext</a>, <a href="https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filtergetinformation">FilterGetInformation</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumeratefilterinformation">FltEnumerateFilterInformation</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilterinformation">FltGetFilterInformation</a>. 

This structure must be aligned on a LONGLONG (8-byte) boundary. If a buffer contains two or more of these structures, the <b>NextEntryOffset</b> value in each entry, except the last, falls on an 8-byte boundary.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltuserstructures/ns-fltuserstructures-_filter_aggregate_basic_information">FILTER_AGGREGATE_BASIC_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltuserstructures/ns-fltuserstructures-_filter_aggregate_standard_information">FILTER_AGGREGATE_STANDARD_INFORMATION</a>



<a href="https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filterfindclose">FilterFindClose</a>



<a href="https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filterfindfirst">FilterFindFirst</a>



<a href="https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filterfindnext">FilterFindNext</a>



<a href="https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filtergetinformation">FilterGetInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumeratefilterinformation">FltEnumerateFilterInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilterinformation">FltGetFilterInformation</a>
 

 

