---
UID: NF:fltkernel.FltQueryInformationFile
title: FltQueryInformationFile function (fltkernel.h)
description: FltQueryInformationFile retrieves information for a given file.
old-location: ifsk\fltqueryinformationfile.htm
tech.root: ifsk
ms.assetid: f80750fb-4561-4617-bc54-1360b2e93a68
ms.date: 04/16/2018
keywords: ["FltQueryInformationFile function"]
ms.keywords: FltApiRef_p_to_z_f6c70c3b-4b99-4ae9-ba01-789c4d3ab1c3.xml, FltQueryInformationFile, FltQueryInformationFile function [Installable File System Drivers], fltkernel/FltQueryInformationFile, ifsk.fltqueryinformationfile
f1_keywords:
 - "fltkernel/FltQueryInformationFile"
 - "FltQueryInformationFile"
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltQueryInformationFile
targetos: Windows
req.typenames: 
---

# FltQueryInformationFile function


## -description


**FltQueryInformationFile** retrieves information for a given file. 


## -parameters




### -param Instance 
[in]
Opaque instance pointer for the caller. This parameter is required and cannot be **NULL**. 


### -param FileObject 
[in]
File object pointer for the file. This parameter is required and cannot be **NULL**. 


### -param FileInformation 
[out]
Pointer to a caller-allocated buffer that receives information about the file. The *FileInformationClass* parameter specifies the type of information. This parameter is required and cannot be **NULL**. 


### -param Length 
[in]
Size, in bytes, of the *FileInformation* buffer. 


### -param FileInformationClass 
[in]
A [FILE_INFORMATION_CLASS](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_file_information_class) value that specifies the type of file information to be returned in the *FileInformation* buffer.


### -param LengthReturned 
[out, optional]
Pointer to a caller-allocated variable that receives the size, in bytes, of the information returned in the *FileInformation* buffer. This parameter is optional and can be **NULL**. 


## -returns

**FltQueryInformationFile** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_VOLUME_DISMOUNTED</dt>
</dl>
</td>
<td width="60%">
The file resides on a volume that is not currently mounted. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



A minifilter driver calls **FltQueryInformationFile** to retrieve information for the file identified by *FileObject*. The file must currently be open. 

**FltQueryInformationFile** returns zero in any member of a FILE_*XXX*_INFORMATION structure that is not supported by a particular file system. 

Callers of **FltQueryInformationFile** must be running at IRQL = PASSIVE_LEVEL and [with APCs enabled](https://docs.microsoft.com/windows-hardware/drivers/kernel/disabling-apcs).

**NOTE:**
Do not call this routine with a non-NULL top level IRP value, as this can cause a system deadlock.

## -see-also

[FILE_INFORMATION_CLASS](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_file_information_class)


[FltQueryVolumeInformationFile](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryvolumeinformationfile)



[FltSetInformationFile](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetinformationfile)



[ZwQueryInformationFile](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile)
 

 

