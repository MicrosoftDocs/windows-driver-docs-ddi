---
UID: NF:ntddk.WheaFindNextErrorRecordSection
title: WheaFindNextErrorRecordSection function (ntddk.h)
description: The WheaFindNextErrorRecordSection function allows a caller to iteratively examine the WHEA error record sections within a WHEA error record. Each error record section is formatted as a WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure.
old-location: whea\wheafindnexterrorrecordsection.htm
tech.root: whea
ms.assetid: 36a0ca45-2601-4b7f-9f2b-35e2a7047520
ms.date: 02/20/2018
ms.keywords: WheaFindNextErrorRecordSection, WheaFindNextErrorRecordSection function [WHEA Drivers and Applications], ntddk/WheaFindNextErrorRecordSection, whea.wheafindnexterrorrecordsection, whearef2_9beb5b85-6c25-49e5-9abc-bcb8e343c8c9.xml
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows 7 and later versions of Windows.
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	WheaFindNextErrorRecordSection
product:
- Windows
targetos: Windows
req.typenames: 
---

# WheaFindNextErrorRecordSection function


## -description


The <b>WheaFindNextErrorRecordSection</b> function allows a caller to iteratively examine the WHEA error record sections within a WHEA <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>. Each error record section is formatted as a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560496">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure.


## -parameters




### -param Record [in]

A pointer to a WHEA <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a> that is formatted as a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560483">WHEA_ERROR_RECORD</a> structure.


### -param Context [in, out]

A pointer to a ULONG variable that maintains the current state of the search. 

<div class="alert"><b>Note</b>  This variable must be initialized to zero before the first call to the <b>WheaFindNextErrorRecordSection </b>function<b>.</b></div>
<div> </div>

### -param SectionDescriptor [out]

The address of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560496">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> pointer. 

If the <b>WheaFindNextErrorRecordSection </b>function locates the next WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure within the specified WHEA <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>, the function sets the <i>SectionDescriptor </i>parameter to the address of that structure within the specified WHEA error record.


### -param SectionData [out, optional]

The address of a PVOID pointer.

If the <b>WheaFindNextErrorRecordSection</b> function locates the next <a href="https://msdn.microsoft.com/library/windows/hardware/ff560496">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure within the specified WHEA <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>, the function sets the <i>SectionData</i> parameter to the address of the hardware error data associated with that descriptor.

<div class="alert"><b>Note</b>  This parameter is optional and must be set to <b>NULL</b> if a pointer to the error record section data is not required.</div>
<div> </div>

## -returns



<b>WheaFindNextErrorRecordSection</b> returns one of the following NTSTATUS codes:

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
The next  <a href="https://msdn.microsoft.com/library/windows/hardware/ff560496">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure was found. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The next <a href="https://msdn.microsoft.com/library/windows/hardware/ff560496">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure was not found.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Either the <i>Record</i>, <i>SectionType,</i> or <i>SectionDescriptor</i> parameters were set to <b>NULL</b>, or the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560483">WHEA_ERROR_RECORD</a> data referenced through the <i>Record </i>parameter is invalid.

</td>
</tr>
</table>
 




## -remarks



If the <i>Context</i> parameter is set to 0, <b>WheaFindNextErrorRecordSection </b>returns a pointer to the first <a href="https://msdn.microsoft.com/library/windows/hardware/ff560496">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure within a WHEA <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>. <b>WheaFindNextErrorRecordSection </b>will also update the <i>Context</i> parameter with state information related to the WHEA_ERROR_RECORD_SECTION_DESCRIPTOR returned through the <i>SectionDescriptor</i> parameter.

On subsequent calls to <b>WheaFindNextErrorRecordSection</b>, the function returns the next WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure (if available) within the WHEA error record. If the function locates the next WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure, it will update the <i>Context</i> parameter. Otherwise, the function will return STATUS_NOT_FOUND.

<div class="alert"><b>Note</b>  In order to locate the first <a href="https://msdn.microsoft.com/library/windows/hardware/ff560496">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> within the specified WHEA <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>, the caller must set the variable, whose address is passed in the <i>Context</i> parameter, to 0 before the calling. After that, the caller must not modify the variable's value when locating the next WHEA_ERROR_RECORD_SECTION_DESCRIPTOR through subsequent calls to <b>WheaFindNextErrorRecordSection</b>.</div>
<div> </div>
Additionally, if <b>WheaFindNextErrorRecordSection</b> returns STATUS_SUCCESS and the caller set the <i>SectionData</i> parameter to the address of a PVOID pointer variable, the function updates the parameter with the address of the hardware error data associated with the specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff560496">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure. 

The format of the hardware error data depends upon the <b>SectionType </b>member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560496">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure that is referenced through the <i>SectionDescriptor </i>parameter. For example, if the <b>SectionType </b>member has the value PROCESSOR_GENERIC_ERROR_SECTION_GUID, the hardware error data is formatted as a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560607">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">Error record</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560483">WHEA_ERROR_RECORD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560496">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>
 

 

