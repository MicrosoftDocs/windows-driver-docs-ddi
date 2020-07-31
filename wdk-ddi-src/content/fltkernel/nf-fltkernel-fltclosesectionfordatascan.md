---
UID: NF:fltkernel.FltCloseSectionForDataScan
title: FltCloseSectionForDataScan function (fltkernel.h)
description: The FltCloseSectionForDataScan routine closes a section object associated with a file stream.
old-location: ifsk\fltclosesectionfordatascan.htm
tech.root: ifsk
ms.assetid: 2B3C52FD-80D7-4ECA-9B33-7916FB47B0B2
ms.date: 04/16/2018
keywords: ["FltCloseSectionForDataScan function"]
ms.keywords: FltCloseSectionForDataScan, FltCloseSectionForDataScan routine [Installable File System Drivers], fltkernel/FltCloseSectionForDataScan, ifsk.fltclosesectionfordatascan
f1_keywords:
 - "fltkernel/FltCloseSectionForDataScan"
 - "FltCloseSectionForDataScan"
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: The FltCloseSectionForDataScan routine is available starting with  Windows 8.
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
req.lib: FltMgr.lib
req.dll: 
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- FltMgr.lib
- FltMgr.dll
api_name:
- FltCloseSectionForDataScan
targetos: Windows
req.typenames: 
---

# FltCloseSectionForDataScan function


## -description


The <b>FltCloseSectionForDataScan</b> routine closes a section object associated with a file stream.


## -parameters




### -param SectionContext [in]

A pointer to the section context to close. 


## -returns



<b>FltCloseSectionForDataScan</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The section context was not properly created. An allocated section context must first be passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatesectionfordatascan">FltCreateSectionForDataScan</a>. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The section context is already closed.

</td>
</tr>
</table>
 




## -remarks



Minifilters use the <b>FltCloseSectionForDataScan</b> routine to deallocate  and remove a section context from a file object. All previously allocated section contexts passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatesectionfordatascan">FltCreateSectionForDataScan</a> must be passed to <b>FltCloseSectionForDataScan</b>. Otherwise, minifilters can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a> if the section context was allocated with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a> but no section was created with  <b>FltCreateSectionForDataScan</b>.

After <b>FltCloseSectionForDataScan</b> returns, operations that conflict with the section  described by <i>SectionContext</i> will not be synchronized by the filter manager.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatesectionfordatascan">FltCreateSectionForDataScan</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletecontext">FltDeleteContext</a>
 

 

