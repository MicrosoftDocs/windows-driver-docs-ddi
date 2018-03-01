---
UID: NF:fltkernel.FltSetInformationFile
title: FltSetInformationFile function
author: windows-driver-content
description: FltSetInformationFile sets information for a given file.
old-location: ifsk\fltsetinformationfile.htm
old-project: ifsk
ms.assetid: 8d0a91ef-9fb0-45a6-979a-614aed1703a5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_p_to_z_310caf59-cf9a-488a-8632-f0d8d5e14769.xml, FltSetInformationFile, FltSetInformationFile function [Installable File System Drivers], fltkernel/FltSetInformationFile, ifsk.fltsetinformationfile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltSetInformationFile
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltSetInformationFile function


## -description


<b>FltSetInformationFile</b> sets information for a given file. 


## -syntax


````
NTSTATUS FltSetInformationFile(
  _In_ PFLT_INSTANCE          Instance,
  _In_ PFILE_OBJECT           FileObject,
  _In_ PVOID                  FileInformation,
  _In_ ULONG                  Length,
  _In_ FILE_INFORMATION_CLASS FileInformationClass
);
````


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
Set <a href="..\ntifs\ns-ntifs-_file_allocation_information.md">FILE_ALLOCATION_INFORMATION</a> for the file. 

</td>
</tr>
<tr>
<td>
<b>FileBasicInformation</b>

</td>
<td>
Set <a href="..\wdm\ns-wdm-_file_basic_information.md">FILE_BASIC_INFORMATION</a> for the file. 

</td>
</tr>
<tr>
<td>
<b>FileDispositionInformation</b>

</td>
<td>
Set <a href="..\ntddk\ns-ntddk-_file_disposition_information.md">FILE_DISPOSITION_INFORMATION</a> for the file. 

</td>
</tr>
<tr>
<td>
<b>FileEndOfFileInformation</b>

</td>
<td>
Set <a href="..\ntddk\ns-ntddk-_file_end_of_file_information.md">FILE_END_OF_FILE_INFORMATION</a> for the file. 

</td>
</tr>
<tr>
<td>
<b>FileLinkInformation</b>

</td>
<td>
Set <a href="..\ntifs\ns-ntifs-_file_link_information.md">FILE_LINK_INFORMATION</a> for the file. 

</td>
</tr>
<tr>
<td>
<b>FilePositionInformation</b>

</td>
<td>
Set <a href="..\wdm\ns-wdm-_file_position_information.md">FILE_POSITION_INFORMATION</a> for the file. 

</td>
</tr>
<tr>
<td>
<b>FileRenameInformation</b>

</td>
<td>
Set <a href="..\ntifs\ns-ntifs-_file_rename_information.md">FILE_RENAME_INFORMATION</a> for the file. For more information about file renaming, see the following Remarks section. 

</td>
</tr>
<tr>
<td>
<b>FileValidDataLengthInformation</b>

</td>
<td>
Set <a href="..\ntddk\ns-ntddk-_file_valid_data_length_information.md">FILE_VALID_DATA_LENGTH_INFORMATION</a> for the file. 

</td>
</tr>
</table>
 


## -returns



<b>FltSetInformationFile</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value. 




## -remarks



A minifilter driver calls <b>FltSetInformationFile</b> to set information for a given file. The file must currently be open. 

A file rename operation imposes the following restriction on the parameter values passed to <b>FltSetInformationFile</b>: As noted in the reference entry for <a href="..\ntifs\ns-ntifs-_file_rename_information.md">FILE_RENAME_INFORMATION</a>, a file or directory can only be renamed within a volume. In other words, a rename operation cannot cause a file or directory to be moved to a different volume. Unlike <a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a>, <b>FltSetInformationFile</b> does not validate the contents of the FILE_RENAME_INFORMATION structure. Thus the caller of <b>FltSetInformationFile</b> is responsible for ensuring that the new name for the file or directory is on the same volume as the old name. 

Minifilter drivers must use <b>FltSetInformationFile</b> , not <a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a>, to rename a file. 




## -see-also

<a href="..\wdm\ns-wdm-_file_position_information.md">FILE_POSITION_INFORMATION</a>



<a href="..\ntifs\ns-ntifs-_file_link_information.md">FILE_LINK_INFORMATION</a>



<a href="..\ntddk\ns-ntddk-_file_end_of_file_information.md">FILE_END_OF_FILE_INFORMATION</a>



<a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformationfile.md">FltQueryVolumeInformationFile</a>



<a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a>



<a href="..\wdm\ns-wdm-_file_basic_information.md">FILE_BASIC_INFORMATION</a>



<a href="..\fltkernel\nf-fltkernel-fltqueryinformationfile.md">FltQueryInformationFile</a>



<a href="..\ntifs\ns-ntifs-_file_rename_information.md">FILE_RENAME_INFORMATION</a>



<a href="..\ntifs\ns-ntifs-_file_allocation_information.md">FILE_ALLOCATION_INFORMATION</a>



<a href="..\ntddk\ns-ntddk-_file_valid_data_length_information.md">FILE_VALID_DATA_LENGTH_INFORMATION</a>



<a href="..\ntddk\ns-ntddk-_file_disposition_information.md">FILE_DISPOSITION_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltSetInformationFile function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

