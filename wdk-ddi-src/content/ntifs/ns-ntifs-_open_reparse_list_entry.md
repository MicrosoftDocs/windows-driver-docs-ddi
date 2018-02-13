---
UID: NS:ntifs._OPEN_REPARSE_LIST_ENTRY
title: "_OPEN_REPARSE_LIST_ENTRY"
author: windows-driver-content
description: This structure supports callers opening specific reparse points without inhibiting reparse behavior for all classes of reparse points.
old-location: ifsk\open_reparse_list_entry_.htm
old-project: ifsk
ms.assetid: A6D28F60-FA38-45EA-9E3C-D2E6F899333E
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: OPEN_REPARSE_POINT_REPARSE_IF_DIRECTORY_FINAL_COMPONENT, OPEN_REPARSE_LIST_ENTRY structure [Installable File System Drivers], OPEN_REPARSE_POINT_REPARSE_IF_CHILD_EXISTS, ntifs/OPEN_REPARSE_LIST_ENTRY, OPEN_REPARSE_POINT_REPARSE_IF_CHILD_NOT_EXISTS, OPEN_REPARSE_LIST_ENTRY, POPEN_REPARSE_LIST_ENTRY structure pointer [Installable File System Drivers], OPEN_REPARSE_POINT_TAG_ENCOUNTERED, ntifs/POPEN_REPARSE_LIST_ENTRY, POPEN_REPARSE_LIST_ENTRY, OPEN_REPARSE_POINT_VERSION_EX, ifsk.open_reparse_list_entry_, _OPEN_REPARSE_LIST_ENTRY, *POPEN_REPARSE_LIST_ENTRY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	OPEN_REPARSE_LIST_ENTRY
product: Windows
targetos: Windows
req.typenames: OPEN_REPARSE_LIST_ENTRY, *POPEN_REPARSE_LIST_ENTRY
---

# _OPEN_REPARSE_LIST_ENTRY structure


## -description


This structure supports callers opening specific reparse points without
inhibiting reparse behavior for all classes of reparse points.


## -syntax


````
typedef struct _OPEN_REPARSE_LIST_ENTRY  {
  LIST_ENTRY OpenReparseListEntry;
  ULONG      ReparseTag;
  ULONG      Flags;
  GUID       ReparseGuid;
  USHORT     Size;
  USHORT     RemainingLength;
} OPEN_REPARSE_LIST_ENTRY , *POPEN_REPARSE_LIST_ENTRY ;
````


## -struct-fields




### -field OpenReparseListEntry

The entry in the open reparse list.


### -field ReparseTag

The reparse tag that should be opened directly without returning <b>STATUS_REPARSE</b>. 


### -field Flags

Flags that control behavior when a reparse point is encountered on a directory that may be non-empty (one whose reparse tag is  recognized by <b>FsRtlIsNonEmptyDirectoryReparsePointAllowed</b>)
.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="OPEN_REPARSE_POINT_TAG_ENCOUNTERED"></a><a id="open_reparse_point_tag_encountered"></a><dl>
<dt><b>OPEN_REPARSE_POINT_TAG_ENCOUNTERED</b></dt>
<dt>0x00000001</dt>
</dl>
</td>
<td width="60%">
Indicates that the object that was opened matched the given criteria.

</td>
</tr>
<tr>
<td width="40%"><a id="OPEN_REPARSE_POINT_REPARSE_IF_CHILD_EXISTS"></a><a id="open_reparse_point_reparse_if_child_exists"></a><dl>
<dt><b>OPEN_REPARSE_POINT_REPARSE_IF_CHILD_EXISTS</b></dt>
<dt>0x00000002</dt>
</dl>
</td>
<td width="60%">
Reparse on the directory if the reparse point is on a directory that is not the final path
    component, and the next path component exists.

</td>
</tr>
<tr>
<td width="40%"><a id="OPEN_REPARSE_POINT_REPARSE_IF_CHILD_NOT_EXISTS"></a><a id="open_reparse_point_reparse_if_child_not_exists"></a><dl>
<dt><b>OPEN_REPARSE_POINT_REPARSE_IF_CHILD_NOT_EXISTS</b></dt>
<dt>0x00000004</dt>
</dl>
</td>
<td width="60%">
Reparse on the directory if the reparse point is on a directory that is not the final path
    component, and the next path component does not exist.

</td>
</tr>
<tr>
<td width="40%"><a id="OPEN_REPARSE_POINT_REPARSE_IF_DIRECTORY_FINAL_COMPONENT"></a><a id="open_reparse_point_reparse_if_directory_final_component"></a><dl>
<dt><b>OPEN_REPARSE_POINT_REPARSE_IF_DIRECTORY_FINAL_COMPONENT</b></dt>
<dt>0x00000008</dt>
</dl>
</td>
<td width="60%">
Reparse on the directory if the reparse point is on a directory that is the final path
component
and <b>FILE_OPEN_REPARSE_POINT</b> has not been specified.

</td>
</tr>
<tr>
<td width="40%"><a id="OPEN_REPARSE_POINT_VERSION_EX"></a><a id="open_reparse_point_version_ex"></a><dl>
<dt><b>OPEN_REPARSE_POINT_VERSION_EX</b></dt>
<dt>0x80000000</dt>
</dl>
</td>
<td width="60%">
Indicates that the fields of this structure are valid.

</td>
</tr>
</table>
 

<div class="alert"><b>Note</b>  When the <b>OPEN_REPARSE_POINT_REPARSE_IF_CHILD_EXISTS</b>,  <b>OPEN_REPARSE_POINT_REPARSE_IF_CHILD_NOT_EXISTS</b>, and <b>OPEN_REPARSE_POINT_REPARSE_IF_DIRECTORY_FINAL_COMPONENT</b> flags are used together at the same time, it indicates that the system is to reparse on any directory reparse point.</div>
<div> </div>

### -field ReparseGuid

The GUID of the reparse tag that should be opened directly without returning <b>STATUS_REPARSE</b>.


### -field Size

The size of this structure.


### -field RemainingLength

The unprocessed path length when the reparse point was
    encountered.


## -remarks



This structure lets callers open specific reparse points without
  inhibiting reparse behavior for all classes of reparse points.
<a href="..\ntifs\ns-ntifs-_open_reparse_list.md">OPEN_REPARSE_LIST</a> is a structure used in an ECP with <b>ECP_TYPE_OPEN_REPARSE_GUID</b> (<code>323eb6a8-affd-4d95-8230-863bce09d37a</code>). The <b>OPEN_REPARSE_LIST</b> points to a list of <b>OPEN_REPARSE_LIST_ENTRY</b>
structures specifying the tag and possibly GUID that should be
  opened directly without returning <b>STATUS_REPARSE</b>.
If a match is found, the corresponding <b>OPEN_REPARSE_LIST_ENTRY</b>  structure will have the <b>OPEN_REPARSE_POINT_TAG_ENCOUNTERED</b> flag set to indicate that the object that was opened matched the given criteria. If a match is found for a directory that is not the final path  component and <b>STATUS_REPARSE</b> is returned, the unprocessed path
  length will be set in the <b>RemainingLength</b> field.



