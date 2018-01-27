---
UID: NS:fltuserstructures._FILTER_AGGREGATE_STANDARD_INFORMATION
title: _FILTER_AGGREGATE_STANDARD_INFORMATION
author: windows-driver-content
description: The FILTER_AGGREGATE_STANDARD_INFORMATION structure contains information about a minifilter or legacy filter driver.
old-location: ifsk\filter_aggregate_standard_information.htm
old-project: ifsk
ms.assetid: 76703a53-45c1-4dfa-b8aa-4f73d4d84538
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: fltuserstructures/PFILTER_AGGREGATE_STANDARD_INFORMATION, FILTER_AGGREGATE_STANDARD_INFORMATION, fltuserstructures/FILTER_AGGREGATE_STANDARD_INFORMATION, _FILTER_AGGREGATE_STANDARD_INFORMATION, PFILTER_AGGREGATE_STANDARD_INFORMATION structure pointer [Installable File System Drivers], FltSystemStructures_2b06b94c-69dc-4b0c-a9bc-56bba1592036.xml, ifsk.filter_aggregate_standard_information, FILTER_AGGREGATE_STANDARD_INFORMATION structure [Installable File System Drivers], PFILTER_AGGREGATE_STANDARD_INFORMATION, *PFILTER_AGGREGATE_STANDARD_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fltuserstructures.h
req.include-header: FltUser.h, FltKernel.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available starting with Windows Vista.
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
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	fltuserstructures.h
apiname: 
-	FILTER_AGGREGATE_STANDARD_INFORMATION
product: Windows
targetos: Windows
req.typenames: *PFILTER_AGGREGATE_STANDARD_INFORMATION, FILTER_AGGREGATE_STANDARD_INFORMATION
---

# _FILTER_AGGREGATE_STANDARD_INFORMATION structure


## -description


The FILTER_AGGREGATE_STANDARD_INFORMATION structure contains information about a minifilter or legacy filter driver.


## -syntax


````
typedef struct _FILTER_AGGREGATE_STANDARD_INFORMATION {
  ULONG NextEntryOffset;
  ULONG Flags;
  union {
    struct {
      ULONG  Flags;
      ULONG  FrameID;
      ULONG  NumberOfInstances;
      USHORT FilterNameLength;
      USHORT FilterNameBufferOffset;
      USHORT FilterAltitudeLength;
      USHORT FilterAltitudeBufferOffset;
    } MiniFilter;
    struct {
      ULONG  Flags;
      USHORT FilterNameLength;
      USHORT FilterNameBufferOffset;
      USHORT FilterAltitudeLength;
      USHORT FilterAltitudeBufferOffset;
    } LegacyFilter;
  } Type;
} FILTER_AGGREGATE_STANDARD_INFORMATION, *PFILTER_AGGREGATE_STANDARD_INFORMATION;
````


## -struct-fields




### -field Type



### -field Type.MiniFilter

Nested structure variable with the following members:


### -field Type.MiniFilter.Flags

There are currently no flags defined for this member.


### -field Type.MiniFilter.FrameID

Zero-based index used to identify the filter manager frame that the minifilter is in.


### -field Type.MiniFilter.NumberOfInstances

Number of instances that currently exist for the minifilter.


### -field Type.MiniFilter.FilterNameLength

Length, in bytes, of the minifilter name string.


### -field Type.MiniFilter.FilterNameBufferOffset

Byte offset (relative to the beginning of the structure) of the first character of the Unicode minifilter name string.  The string is not NULL-terminated.


### -field Type.MiniFilter.FilterAltitudeLength

Length, in bytes, of the minifilter altitude string.


### -field Type.MiniFilter.FilterAltitudeBufferOffset

Byte offset (relative to the beginning of the structure) of the first character of the Unicode minifilter altitude string. The string is not NULL-terminated.


### -field Type.LegacyFilter

Nested structure variable with the following members:


### -field Type.LegacyFilter.Flags

There are currently no flags defined for this member.


### -field Type.LegacyFilter.FilterNameLength

Length, in bytes, of the legacy filter name string.


### -field Type.LegacyFilter.FilterNameBufferOffset

Byte offset (relative to the beginning of the structure) of the first character of the Unicode legacy filter name string.  The string is not NULL-terminated.


### -field Type.LegacyFilter.FilterAltitudeLength

Length, in bytes, of the legacy filter altitude string.


### -field Type.LegacyFilter.FilterAltitudeBufferOffset

Byte offset (relative to the beginning of the structure) of the first character of the Unicode legacy filter altitude string.  The string is not NULL-terminated.

Starting with Windows Vista, altitudes are assigned to legacy filter drivers based on the driver's load order group.  This ensures that minifilter drivers will layer properly above and below legacy filter drivers even if one or more of the filter drivers are loaded out-of-order.


### -field NextEntryOffset

Byte offset of the next FILTER_AGGREGATE_STANDARD_INFORMATION entry, if multiple entries are present in a buffer. This member is zero if no other entries follow this one.


### -field Flags

Indicates whether the filter driver is a legacy filter or a minifilter.  This member must be one of the following values.
<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FLTFL_ASI_IS_MINIFILTER

</td>
<td>
The filter is a minifilter - use the <b>MiniFilter</b> portion of the union.

</td>
</tr>
<tr>
<td>
FLTFL_ASI_IS_LEGACYFILTER

</td>
<td>
The filter is a legacy filter - use the <b>LegacyFilter</b> portion of the union.

</td>
</tr>
</table> 


## -remarks


The FILTER_AGGREGATE_STANDARD_INFORMATION structure can be allocated from paged or nonpaged pool.  This structure is passed as a parameter to routines such as:
<ul>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540485">FilterFindFirst</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540488">FilterFindNext</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540500">FilterGetInformation</a>


</li>
<li>

<a href="..\fltkernel\nf-fltkernel-fltenumeratefilterinformation.md">FltEnumerateFilterInformation</a>


</li>
<li>

<a href="..\fltkernel\nf-fltkernel-fltgetfilterinformation.md">FltGetFilterInformation</a>


</li>
</ul>The FILTER_AGGREGATE_STANDARD_INFORMATION structure must be aligned on a LONGLONG (8-byte) boundary. If a buffer contains two or more of these structures, the <b>NextEntryOffset</b> value in each entry falls on an 8-byte boundary.



## -see-also

<a href="..\fltkernel\nf-fltkernel-fltenumeratefilterinformation.md">FltEnumerateFilterInformation</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540488">FilterFindNext</a>

<a href="..\fltuserstructures\ns-fltuserstructures-_filter_full_information.md">FILTER_FULL_INFORMATION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540485">FilterFindFirst</a>

<a href="..\fltuserstructures\ns-fltuserstructures-_filter_aggregate_basic_information.md">FILTER_AGGREGATE_BASIC_INFORMATION</a>

<a href="..\fltkernel\nf-fltkernel-fltgetfilterinformation.md">FltGetFilterInformation</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540500">FilterGetInformation</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILTER_AGGREGATE_STANDARD_INFORMATION structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

