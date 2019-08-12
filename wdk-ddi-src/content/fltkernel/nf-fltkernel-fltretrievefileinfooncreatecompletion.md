---
UID: NF:fltkernel.FltRetrieveFileInfoOnCreateCompletion
title: FltRetrieveFileInfoOnCreateCompletion function
author: windows-driver-content
description: FltRetrieveFileInfoOnCreateCompletion retrieves the requested file information during file post create.
tech.root: ifsk
ms.assetid: 8ec28ac7-c87c-4e18-bfd0-0266b805cd9d
ms.author: windowsdriverdev
ms.date: 3/12/2019
ms.topic: function
f1_keywords:
 - "fltkernel/FltRetrieveFileInfoOnCreateCompletion"
ms.keywords: FltRetrieveFileInfoOnCreateCompletion
req.header: fltkernel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
 - apiref
api_type: 
 - 
api_location: 
- fltkernel.h
api_name: 
 - FltRetrieveFileInfoOnCreateCompletion
product: 
 - Windows
targetos: Windows

---

# FltRetrieveFileInfoOnCreateCompletion function

## -description

**FltRetrieveFileInfoOnCreateCompletion** retrieves the requested file information during file post create. Use [FltRetrieveFileInfoOnCreateCompletionEx](nf-fltkernel-fltretrievefileinfooncreatecompletionex.md) to get an NTSTATUS code along with the file information.

## -parameters

### -param Filter

Opaque filter pointer that uniquely identifies the minifilter driver.

### -param Data

Pointer to the [FLT_CALLBACK_DATA](ns-fltkernel-_flt_callback_data.md) callback data representing the I/O operation.

### -param InfoClass

Flag that indicates the type of information to return. Note that flags cannot be combined. Can be one of the following values:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>QoCFileStatInformation</b></dt>
0x00000001
</dl>
</td>

<td width="60%">
The file system will return file stat information in a QUERY_ON_CREATE_FILE_STAT_INFORMATION structure.
</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>QoCFileLxInformation</b></dt>
0x00000002
</dl>
</td>
<td width="60%">
The file system will return extended Linux-like information in a QUERY_ON_CREATE_FILE_LX_INFORMATION structure.
</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>QoCFileEaInformation</b></dt>
0x00000004
</dl>
</td>
<td width="60%">
The file system will return extended attributes (EA) in a QUERY_ON_CREATE_EA_INFORMATION structure.
</td>
</tr>

</table>

### Size

Pointer to a ULONG that specifies the size, in bytes, of the buffer that this function returns.

## -returns

**FltRetrieveFileInfoOnCreateCompletion** returns a pointer to a buffer with the requested file information. The structure within the buffer is determined by the value of *InfoClass*. If the file system processes the request but can't find the requested file information, this parameter is set to NULL.

## -remarks

A minifilter must call **FltRequestFileInfoOnCreateCompletion** during file pre-create to specify which file information the file system should track.

## -see-also

[FLT_CALLBACK_DATA](ns-fltkernel-_flt_callback_data.md)

[FltRequestFileInfoOnCreateCompletion](nf-fltkernel-_fltrequestfileinfooncreatecompletion.md)

[FltRetrieveFileInfoOnCreateCompletionEx](nf-fltkernel-fltretrievefileinfooncreatecompletionex.md)
