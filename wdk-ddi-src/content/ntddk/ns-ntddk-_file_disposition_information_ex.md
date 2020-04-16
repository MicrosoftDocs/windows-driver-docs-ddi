---
UID: NS:ntddk._FILE_DISPOSITION_INFORMATION_EX
title: _FILE_DISPOSITION_INFORMATION_EX (ntddk.h)
description: The FILE_DISPOSITION_INFORMATION_EX structure is used as an argument to the ZwSetInformationFile routine and indicates how the operating system should delete a file.
old-location: ifsk\file_disposition_information_ex.htm
tech.root: ifsk
ms.assetid: CCFE4B09-F942-4D89-9013-159066D8E37A
ms.date: 04/16/2018
keywords: ["_FILE_DISPOSITION_INFORMATION_EX structure"]
ms.keywords: "*PFILE_DISPOSITION_INFORMATION_EX, FILE_DISPOSITION_INFORMATION_EX, FILE_DISPOSITION_INFORMATION_EX structure [Installable File System Drivers], PFILE_DISPOSITION_INFORMATION_EX, PFILE_DISPOSITION_INFORMATION_EX structure pointer [Installable File System Drivers], _FILE_DISPOSITION_INFORMATION_EX, ifsk.file_disposition_information_ex, ntddk/FILE_DISPOSITION_INFORMATION_EX, ntddk/PFILE_DISPOSITION_INFORMATION_EX"
f1_keywords:
 - "ntddk/FILE_DISPOSITION_INFORMATION_EX"
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddk.h
api_name:
- FILE_DISPOSITION_INFORMATION_EX
product:
- Windows
targetos: Windows
req.typenames: FILE_DISPOSITION_INFORMATION_EX, *PFILE_DISPOSITION_INFORMATION_EX
---

# _FILE_DISPOSITION_INFORMATION_EX structure


## -description


The <b>FILE_DISPOSITION_INFORMATION_EX</b> structure is used as an argument to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwsetinformationfile">ZwSetInformationFile</a> routine and indicates how the operating system should delete a file.


## -struct-fields




### -field Flags

Specifies what action(s) the system should take with a specific file while deleting.

<table>
<tr>
<th>Flag Name</th>
<th>
                   Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>FILE_DISPOSITION_DO_NOT_DELETE</td>
<td>
                  0x00000000
                </td>
<td>Specifies the system should not delete a file.</td>
</tr>
<tr>
<td>FILE_DISPOSITION_DELETE</td>
<td>0x00000001</td>
<td>Specifies the system should delete a file.</td>
</tr>
<tr>
<td>FILE_DISPOSITION_POSIX_SEMANTICS</td>
<td>0x00000002</td>
<td>Specifies the system should perform a POSIX-style delete. See more info in Remarks.</td>
</tr>
<tr>
<td>FILE_DISPOSITION_FORCE_IMAGE_SECTION_CHECK</td>
<td>0x00000004</td>
<td>Specifies the system should force an image section check. </td>
</tr>
<tr>
<td>FILE_DISPOSITION_ON_CLOSE </td>
<td>0x00000008</td>
<td>Specifies if the system sets or clears the on-close state.</td>
</tr>
<tr>
<td>FILE_DISPOSITION_IGNORE_READONLY_ATTRIBUTE</td>
<td>0x00000010</td>
  <td>Allows read-only files to be deleted. See more info in Remarks.</td>
</tr>
</table>
 


## -remarks



The caller must have DELETE access to a given file to call ZwSetInformationFile with <b>FILE_DISPOSITION_DELETE</b>. 


When <b>FILE_DISPOSITION_POSIX_SEMANTICS</b> is not set, a file marked for deletion is not actually deleted until all open handles for the file have been closed and the link count for the file is zero.  When <b>FILE_DISPOSITION_POSIX_SEMANTICS</b> is set, the link is removed from the visible namespace as soon as the POSIX delete handle has been closed, but the file’s data streams remain accessible by other existing handles until the last handle has been closed. That is, applications that already had the file open can still use their handle to read/write even though the name they used to open it is gone and the file's link count may have reached zero.

If the file is being deleted at user request, using POSIX semantics allows the system to delete the file as requested, but also allows any process with an open handle to continue to access the file's data as long as the handle is open.

A return value of STATUS_CANNOT_DELETE indicates that either the file is read-only, or there's an existing mapped view to the file.  Specifying <b>FILE_DISPOSITION_IGNORE_READONLY_ATTRIBUTE</b> avoids this return value due to the file being read-only, provided the caller has FILE_WRITE_ATTRIBUTES access to the file (the access that would be required to clear the read-only attribute).

## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwclose">ZwClose</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwsetinformationfile">ZwSetInformationFile</a>
 

 

