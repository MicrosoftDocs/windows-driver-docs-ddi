---
UID: NF:fltkernel.FltRequestFileInfoOnCreateCompletion
title: FltRequestFileInfoOnCreateCompletion function
author: windows-driver-content
description: A minifilter calls FltRequestFileInfoOnCreateCompletion during file pre-create to request that the file manager stores the specified file information for retrieval upon create complete.
tech.root: ifsk
ms.assetid:  d33f4ab5-9f50-42d6-8944-0836e090a67a
ms.author: windowsdriverdev
ms.date: 1/11/2019
ms.topic: function
ms.keywords: FltRequestFileInfoOnCreateCompletion, FltRetrieveFileInfoOnCreateCompletion, FltRetrieveFileInfoOnCreateCompletionEx
req.header: fltkernel.h
req.include-header: Fltkernel.h
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
 - 
api_name: 
 - FltRequestFileInfoOnCreateCompletion
product: 
 - Windows
targetos: Windows

---

# FltRequestFileInfoOnCreateCompletion function

## -description

A minifilter calls **FltRequestFileInfoOnCreateCompletion** during file pre-create to request that the file manager store file information for retrieval during post create.

## -parameters

### -param Filter

Opaque filter pointer that uniquely identifies the minifilter driver.

### -param Data

Pointer to the [FLT_CALLBACK_DATA](ns-fltkernel-_flt_callback_data.md) callback data representing the I/O create operation.

### -param InfoClassFlags

Flag bitmask indicating the type of file information that the file system should store for retrieval during post create. Can be any combination of the following flags:

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
If set, the file system will store file stat information in a QUERY_ON_CREATE_FILE_STAT_INFORMATION structure for retrieval.
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
If set, the file system will store extended Linux-like information in a QUERY_ON_CREATE_FILE_LX_INFORMATION structure for retrieval.
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
If set, the file system will store extended attributes (EA) in a QUERY_ON_CREATE_EA_INFORMATION structure for retrieval.
</td>
</tr>

</table>

## -returns

<b>FltRequestFileInfoOnCreateCompletion</b> can return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The file system successfully stored the requested file information.
</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>FltRequestFileInfoOnCreateCompletion</b> was unable to allocate sufficient memory in which to store the requested file information.
</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
The provided callback data object was not an IRP-based create operation.
</td>
</tr>

</table>

## -remarks

The minifilter can retrieve the file information by calling [FltRetrieveFileInfoOnCreateCompletionEx](nf-fltkernel-fltretrieveFileInfoOnCreateCompletionEx) or [FltRetrieveFileInfoOnCreateCompletion](nf-fltkernel-fltretrieveFileInfoOnCreateCompletion) during post create. A minifilter's performance is typically better when it requests and retrieves file information in this manner, rather than querying file information at a later time.

## -see-also

[FLT_CALLBACK_DATA](ns-fltkernel-_flt_callback_data.md)

[FltRetrieveFileInfoOnCreateCompletion](nf-fltkernel-_fltretrievefileinfooncreatecompletion.md)

[FltRetrieveFileInfoOnCreateCompletionEx](nf-fltkernel-fltretrieveFileInfoOnCreateCompletionEx)