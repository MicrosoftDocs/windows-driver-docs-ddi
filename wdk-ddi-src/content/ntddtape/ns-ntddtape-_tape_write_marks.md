---
UID: NS:ntddtape._TAPE_WRITE_MARKS
title: "_TAPE_WRITE_MARKS"
author: windows-driver-content
description: The TAPE_WRITE_MARKS structure is used in conjunction with an IOCTL_TAPE_WRITE_MARKS request to write a setmark, a filemark, a short filemark, or a long filemark to tape.
old-location: storage\tape_write_marks.htm
tech.root: storage
ms.assetid: 5baa7fd0-e806-4da8-9c87-c86ebc003e60
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PTAPE_WRITE_MARKS, PTAPE_WRITE_MARKS, PTAPE_WRITE_MARKS structure pointer [Storage Devices], TAPE_WRITE_MARKS, TAPE_WRITE_MARKS structure [Storage Devices], _TAPE_WRITE_MARKS, ntddtape/PTAPE_WRITE_MARKS, ntddtape/TAPE_WRITE_MARKS, storage.tape_write_marks, structs-tape_18332ea5-6bfb-4acf-8c84-0a77ded0cc72.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddtape.h
req.include-header: Ntddtape.h, Minitape.h
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
-	ntddtape.h
api_name:
-	TAPE_WRITE_MARKS
product:
- Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# _TAPE_WRITE_MARKS structure


## -description


The TAPE_WRITE_MARKS structure is used in conjunction with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560641">IOCTL_TAPE_WRITE_MARKS</a> request to write a setmark, a filemark, a short filemark, or a long filemark to tape. 


## -struct-fields




### -field Type

Indicates the type of mark to write. This member can have one of the following values: 

<table>
<tr>
<th>Type</th>
<th>Meaning</th>
</tr>
<tr>
<td>
TAPE_SETMARKS

</td>
<td>
Writes the number of setmarks specified by <b>Count</b>.

</td>
</tr>
<tr>
<td>
TAPE_FILEMARKS

</td>
<td>
Writes the number of filemarks specified by the <b>Count</b> parameter.

</td>
</tr>
<tr>
<td>
TAPE_SHORT_FILEMARKS

</td>
<td>
Writes the number of short filemarks specified by <b>Count</b>.

</td>
</tr>
<tr>
<td>
TAPE_LONG_FILEMARKS 

</td>
<td>
Writes the number of long filemarks specified by <b>Count</b>.

</td>
</tr>
</table>
 


### -field Count

Indicates the number of marks to write. 


### -field Immediate

When set to <b>TRUE</b>, indicates that the target device should return status immediately. When set to <b>FALSE</b>, indicates that the device should return status after the operation is complete.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560641">IOCTL_TAPE_WRITE_MARKS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567958">TapeMiniWriteMarks</a>
 

 

