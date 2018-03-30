---
UID: NS:ntifs._QUERY_FILE_LAYOUT_OUTPUT
title: "_QUERY_FILE_LAYOUT_OUTPUT"
author: windows-driver-content
description: The QUERY_FILE_LAYOUT_OUTPUT structure serves as a header for the file layout entries that are returned from a FSCTL_QUERY_FILE_LAYOUT request.
old-location: ifsk\query_file_layout_output.htm
old-project: ifsk
ms.assetid: 204893BE-8B89-4BE4-BEDB-BF28DBAAACE9
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PQUERY_FILE_LAYOUT_OUTPUT, PQUERY_FILE_LAYOUT_OUTPUT, PQUERY_FILE_LAYOUT_OUTPUT structure pointer [Installable File System Drivers], QUERY_FILE_LAYOUT_OUTPUT, QUERY_FILE_LAYOUT_OUTPUT structure [Installable File System Drivers], QUERY_FILE_LAYOUT_SINGLE_INSTANCED, _QUERY_FILE_LAYOUT_OUTPUT, ifsk.query_file_layout_output, ntifs/PQUERY_FILE_LAYOUT_OUTPUT, ntifs/QUERY_FILE_LAYOUT_OUTPUT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting in Windows 8.
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
-	Ntifs.h
api_name:
-	QUERY_FILE_LAYOUT_OUTPUT
product: Windows
targetos: Windows
req.typenames: QUERY_FILE_LAYOUT_OUTPUT, *PQUERY_FILE_LAYOUT_OUTPUT
---

# _QUERY_FILE_LAYOUT_OUTPUT structure


## -description


The <b>QUERY_FILE_LAYOUT_OUTPUT</b> structure serves as a header for the file layout entries that are returned from a <a href="https://msdn.microsoft.com/library/windows/hardware/hh451133">FSCTL_QUERY_FILE_LAYOUT</a> request.


## -struct-fields




### -field FileEntryCount

The number of file entries that follow this structure.


### -field FirstFileOffset

The offset in the user buffer for the first file entry.


### -field Flags

Indicates the format of layout entries returned. Can be 0 or the following:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="QUERY_FILE_LAYOUT_SINGLE_INSTANCED"></a><a id="query_file_layout_single_instanced"></a><dl>
<dt><b>QUERY_FILE_LAYOUT_SINGLE_INSTANCED</b></dt>
</dl>
</td>
<td width="60%">
Single instances of stream and file layout entries are returned. When set, only one <b>STREAM_LAYOUT_ENTRY</b> structure is returned per stream and only one <b>FILE_LAYOUT_ENTRY</b> structure is returned per file. This flag is always set for NTFS.

</td>
</tr>
</table>
 


### -field Reserved

Reserved.


## -remarks



The file layout entries that follow the <b>QUERY_FILE_LAYOUT_OUTPUT</b> structure are determined by the flags set in the <b>Flags</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/hh439457">QUERY_FILE_LAYOUT_INPUT</a> provided as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451133">FSCTL_QUERY_FILE_LAYOUT</a> request. A number of <b>FILE_LAYOUT_ENTRY</b> structures follow <b>QUERY_FILE_LAYOUT_OUTPUT</b>. Depending on the entries selected to return from a query, offsets in <b>FILE_LAYOUT_ENTRY</b> indicate where the additional informational entries are located in the user buffer. 

The following entry structures are returned when their corresponding inclusion flag is set in the <b>Flags</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/hh439457">QUERY_FILE_LAYOUT_INPUT</a>.<table>
<tr>
<th>Entry</th>
<th>Inclusion flag</th>
</tr>
<tr>
<td><b>FILE_LAYOUT_NAME_ENTRY</b></td>
<td><b>QUERY_FILE_LAYOUT_INCLUDE_NAMES</b></td>
</tr>
<tr>
<td><b>FILE_LAYOUT_INFO_ENTRY</b></td>
<td><b>QUERY_FILE_LAYOUT_INCLUDE_EXTRA_INFO</b></td>
</tr>
<tr>
<td><b>STREAM_LAYOUT_ENTRY</b></td>
<td><b>QUERY_FILE_LAYOUT_INCLUDE_STREAMS</b></td>
</tr>
<tr>
<td><b>STREAM_EXTENT_ENTRY</b></td>
<td><b>QUERY_FILE_LAYOUT_INCLUDE_EXTENTS</b></td>
</tr>
</table>
 



When multiple entries of the same type exist for a single <b>FILE_LAYOUT_ENTRY</b> structure, each informational entry structure has an offset member that indicates the location of the next entry. The chain of entry structures continues until the value of the offset member is 0.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451133">FSCTL_QUERY_FILE_LAYOUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439457">QUERY_FILE_LAYOUT_INPUT</a>
 

 

