---
UID: NF:fltkernel.FltSetInformationFile
title: FltSetInformationFile function (fltkernel.h)
description: FltSetInformationFile sets information for a given file.
old-location: ifsk\fltsetinformationfile.htm
tech.root: ifsk
ms.assetid: 8d0a91ef-9fb0-45a6-979a-614aed1703a5
ms.date: 04/16/2018
keywords: ["FltSetInformationFile function"]
ms.keywords: FltApiRef_p_to_z_310caf59-cf9a-488a-8632-f0d8d5e14769.xml, FltSetInformationFile, FltSetInformationFile function [Installable File System Drivers], fltkernel/FltSetInformationFile, ifsk.fltsetinformationfile
f1_keywords:
 - "fltkernel/FltSetInformationFile"
 - "FltSetInformationFile"
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltSetInformationFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltSetInformationFile function


## -description


<b>FltSetInformationFile</b> sets information for a given file. 


## -parameters




### -param Instance [in]

Opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


### -param FileObject [in]

File object pointer for the file. This parameter is required and cannot be <b>NULL</b>. 


### -param FileInformation [in]

Pointer to a caller-allocated buffer that contains information to be set for the file. The <i>FileInformationClass</i> parameter specifies the type of information. This parameter is required and cannot be <b>NULL</b>. 


### -param Length [in]

Size, in bytes, of the <i>FileInformation</i> buffer. 


### -param FileInformationClass [in]

Specifies the type of information to be set for the file. The following values are defined. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>FileAllocationInformation</b>

</td>
<td>
Set <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_allocation_information">FILE_ALLOCATION_INFORMATION</a> for the file. 

</td>
</tr>
<tr>
<td>
<b>FileBasicInformation</b>

</td>
<td>
Set <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_basic_information">FILE_BASIC_INFORMATION</a> for the file. 

</td>
</tr>
<tr>
<td>
<b>FileDispositionInformation</b>

</td>
<td>
Set <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_disposition_information">FILE_DISPOSITION_INFORMATION</a> for the file. 

</td>
</tr>
<tr>
<td>
<b>FileEndOfFileInformation</b>

</td>
<td>
Set <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_end_of_file_information">FILE_END_OF_FILE_INFORMATION</a> for the file. 

</td>
</tr>
<tr>
<td>
<b>FileLinkInformation</b>

</td>
<td>
Set <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_link_information">FILE_LINK_INFORMATION</a> for the file. 

</td>
</tr>
<tr>
<td>
<b>FilePositionInformation</b>

</td>
<td>
Set <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_position_information">FILE_POSITION_INFORMATION</a> for the file. 

</td>
</tr>
<tr>
<td>
<b>FileRenameInformation</b>

</td>
<td>
Set <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_rename_information">FILE_RENAME_INFORMATION</a> for the file. For more information about file renaming, see the following Remarks section. 

</td>
</tr>
<tr>
<td>
<b>FileValidDataLengthInformation</b>

</td>
<td>
Set <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_valid_data_length_information">FILE_VALID_DATA_LENGTH_INFORMATION</a> for the file. 

</td>
</tr>
</table>
 


## -returns



<b>FltSetInformationFile</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value. 




## -remarks



A minifilter driver calls <b>FltSetInformationFile</b> to set information for a given file. The file must currently be open. 

A file rename operation imposes the following restriction on the parameter values passed to <b>FltSetInformationFile</b>: As noted in the reference entry for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_rename_information">FILE_RENAME_INFORMATION</a>, a file or directory can only be renamed within a volume. In other words, a rename operation cannot cause a file or directory to be moved to a different volume. Unlike <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntsetinformationfile">ZwSetInformationFile</a>, <b>FltSetInformationFile</b> does not validate the contents of the FILE_RENAME_INFORMATION structure. Thus the caller of <b>FltSetInformationFile</b> is responsible for ensuring that the new name for the file or directory is on the same volume as the old name. 

Minifilter drivers must use <b>FltSetInformationFile</b> , not <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntsetinformationfile">ZwSetInformationFile</a>, to rename a file. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_allocation_information">FILE_ALLOCATION_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_basic_information">FILE_BASIC_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_disposition_information">FILE_DISPOSITION_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_end_of_file_information">FILE_END_OF_FILE_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_link_information">FILE_LINK_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_position_information">FILE_POSITION_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_rename_information">FILE_RENAME_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_valid_data_length_information">FILE_VALID_DATA_LENGTH_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryinformationfile">FltQueryInformationFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryvolumeinformationfile">FltQueryVolumeInformationFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntsetinformationfile">ZwSetInformationFile</a>
 

 

