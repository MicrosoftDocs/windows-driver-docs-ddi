---
UID: NF:ntddk.WheaFindNextErrorRecordSection
title: WheaFindNextErrorRecordSection function
author: windows-driver-content
description: The WheaFindNextErrorRecordSection function allows a caller to iteratively examine the WHEA error record sections within a WHEA error record. Each error record section is formatted as a WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure.
old-location: whea\wheafindnexterrorrecordsection.htm
old-project: whea
ms.assetid: 36a0ca45-2601-4b7f-9f2b-35e2a7047520
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: whea.wheafindnexterrorrecordsection, WheaFindNextErrorRecordSection, ntddk/WheaFindNextErrorRecordSection, WheaFindNextErrorRecordSection function [WHEA Drivers and Applications], whearef2_9beb5b85-6c25-49e5-9abc-bcb8e343c8c9.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	WheaFindNextErrorRecordSection
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# WheaFindNextErrorRecordSection function


## -description


The <b>WheaFindNextErrorRecordSection</b> function allows a caller to iteratively examine the WHEA error record sections within a WHEA <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>. Each error record section is formatted as a <a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure.


## -syntax


````
NTSTATUS WheaFindNextErrorRecordSection(
  _In_      PWHEA_ERROR_RECORD                    Record,
  _Inout_   ULONG                                 *Context,
  _Out_     PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR *SectionDescriptor,
  _Out_opt_ PVOID                                 *SectionData
);
````


## -parameters




### -param Record [in]

A pointer to a WHEA <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a> that is formatted as a <a href="..\ntddk\ns-ntddk-_whea_error_record.md">WHEA_ERROR_RECORD</a> structure.


### -param Context [in, out]

A pointer to a ULONG variable that maintains the current state of the search. 
<div class="alert"><b>Note</b>  This variable must be initialized to zero before the first call to the <b>WheaFindNextErrorRecordSection </b>function<b>.</b></div><div> </div>

### -param SectionDescriptor [out]

The address of a <a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> pointer. 

If the <b>WheaFindNextErrorRecordSection </b>function locates the next WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure within the specified WHEA <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>, the function sets the <i>SectionDescriptor </i>parameter to the address of that structure within the specified WHEA error record.


### -param SectionData [out, optional]

The address of a PVOID pointer.

If the <b>WheaFindNextErrorRecordSection</b> function locates the next <a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure within the specified WHEA <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>, the function sets the <i>SectionData</i> parameter to the address of the hardware error data associated with that descriptor.
<div class="alert"><b>Note</b>  This parameter is optional and must be set to <b>NULL</b> if a pointer to the error record section data is not required.</div><div> </div>

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
The next  <a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure was found. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The next <a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure was not found.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Either the <i>Record</i>, <i>SectionType,</i> or <i>SectionDescriptor</i> parameters were set to <b>NULL</b>, or the <a href="..\ntddk\ns-ntddk-_whea_error_record.md">WHEA_ERROR_RECORD</a> data referenced through the <i>Record </i>parameter is invalid.

</td>
</tr>
</table> 



## -remarks


If the <i>Context</i> parameter is set to 0, <b>WheaFindNextErrorRecordSection </b>returns a pointer to the first <a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure within a WHEA <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>. <b>WheaFindNextErrorRecordSection </b>will also update the <i>Context</i> parameter with state information related to the WHEA_ERROR_RECORD_SECTION_DESCRIPTOR returned through the <i>SectionDescriptor</i> parameter.

On subsequent calls to <b>WheaFindNextErrorRecordSection</b>, the function returns the next WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure (if available) within the WHEA error record. If the function locates the next WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure, it will update the <i>Context</i> parameter. Otherwise, the function will return STATUS_NOT_FOUND.
<div class="alert"><b>Note</b>  In order to locate the first <a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> within the specified WHEA <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>, the caller must set the variable, whose address is passed in the <i>Context</i> parameter, to 0 before the calling. After that, the caller must not modify the variable's value when locating the next WHEA_ERROR_RECORD_SECTION_DESCRIPTOR through subsequent calls to <b>WheaFindNextErrorRecordSection</b>.</div><div> </div>Additionally, if <b>WheaFindNextErrorRecordSection</b> returns STATUS_SUCCESS and the caller set the <i>SectionData</i> parameter to the address of a PVOID pointer variable, the function updates the parameter with the address of the hardware error data associated with the specified <a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure. 

The format of the hardware error data depends upon the <b>SectionType </b>member of the <a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure that is referenced through the <i>SectionDescriptor </i>parameter. For example, if the <b>SectionType </b>member has the value PROCESSOR_GENERIC_ERROR_SECTION_GUID, the hardware error data is formatted as a <a href="..\ntddk\ns-ntddk-_whea_processor_generic_error_section.md">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a> structure.



## -see-also

<a href="..\ntddk\ns-ntddk-_whea_error_record.md">WHEA_ERROR_RECORD</a>

<a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a>

<a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">Error record</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WheaFindNextErrorRecordSection function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

