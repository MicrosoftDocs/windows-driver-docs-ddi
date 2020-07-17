---
UID: NF:ntddk.WheaFindErrorRecordSection
title: WheaFindErrorRecordSection function (ntddk.h)
description: The WheaFindErrorRecordSection function searches for a specified Windows Hardware Error Architecture (WHEA) error record section within a WHEA error record. The error record section is formatted as a WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure.
old-location: whea\wheafinderrorrecordsection.htm
tech.root: whea
ms.assetid: 57c94f04-82e2-4790-b198-d415e494d70b
ms.date: 02/20/2018
keywords: ["WheaFindErrorRecordSection function"]
ms.keywords: WheaFindErrorRecordSection, WheaFindErrorRecordSection function [WHEA Drivers and Applications], ntddk/WheaFindErrorRecordSection, whea.wheafinderrorrecordsection, whearef2_fe7f8220-081d-475c-9230-d59cff81164d.xml
f1_keywords:
 - "ntddk/WheaFindErrorRecordSection"
 - "WheaFindErrorRecordSection"
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddk.h
api_name:
- WheaFindErrorRecordSection
product:
- Windows
targetos: Windows
req.typenames: 
---

# WheaFindErrorRecordSection function


## -description


The <b>WheaFindErrorRecordSection</b> function searches for a specified Windows Hardware Error Architecture (WHEA) error record section within a WHEA <a href="https://docs.microsoft.com/windows-hardware/drivers/whea/error-records">error record</a>. The error record section is formatted as a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure.


## -parameters




### -param Record [in]

A pointer to a WHEA <a href="https://docs.microsoft.com/windows-hardware/drivers/whea/error-records">error record</a> that is formatted as a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record">WHEA_ERROR_RECORD</a> structure.


### -param SectionType [in]

A GUID that specifies the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure to be located within the specified WHEA <a href="https://docs.microsoft.com/windows-hardware/drivers/whea/error-records">error record</a>.


### -param SectionDescriptor [out]

The address of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> pointer. 

If the <b>WheaFindErrorRecordSection</b> function locates the specified WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure, the function sets the <i>SectionDescriptor </i>parameter to the address of that structure within the specified WHEA <a href="https://docs.microsoft.com/windows-hardware/drivers/whea/error-records">error record</a>.


### -param SectionData [out, optional]

The address of a PVOID pointer.

If the <b>WheaFindErrorRecordSection</b> function locates the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure, the function sets the <i>SectionData</i> parameter to the address of the hardware error data associated with that descriptor within the specified WHEA <a href="https://docs.microsoft.com/windows-hardware/drivers/whea/error-records">error record</a>.

<div class="alert"><b>Note</b>  This parameter is optional and must be set to <b>NULL</b> if a pointer to the hardware error data is not required.</div>
<div> </div>

## -returns



<b>WheaFindErrorRecordSection</b> returns one of the following NTSTATUS codes:

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
The specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure was found. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure was not found.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Either the <i>Record</i>, <i>SectionType,</i> or <i>SectionDescriptor</i> parameters were set to <b>NULL</b>, or the WHEA <a href="https://docs.microsoft.com/windows-hardware/drivers/whea/error-records">error record</a> referenced through the <i>Record </i>parameter is invalid.

</td>
</tr>
</table>
 




## -remarks



If <b>WheaFindErrorRecordSection</b> returns STATUS_SUCCESS, it has located the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure that was specified through the <i>Guid </i>parameter. <b>WheaFindErrorRecordSection</b> sets the <i>SectionDescriptor</i> parameter to the address of the located <b>WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</b> structure.

Additionally, if <b>WheaFindErrorRecordSection</b> returns STATUS_SUCCESS and the caller set the <i>SectionData</i> parameter to the address of a PVOID pointer variable, the function updates the parameter with the address of the hardware error data associated with the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure. 

The format of the hardware error data is dependent upon the <b>SectionType </b>member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure referenced through the <i>SectionDescriptor </i>parameter. For example, if the <b>SectionType </b>member has the value PROCESSOR_GENERIC_ERROR_SECTION_GUID, the hardware error data is formatted as a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_processor_generic_error_section">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/whea/error-records">Error record</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record">WHEA_ERROR_RECORD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>
 

 

