---
UID: NF:fltkernel.FltQueryDirectoryFile
title: FltQueryDirectoryFile function
author: windows-driver-content
description: The FltQueryDirectoryFile routine returns various kinds of information about files in the directory specified by a given file object.
old-location: ifsk\fltquerydirectoryfile.htm
old-project: ifsk
ms.assetid: d77dfcc7-a7a7-4027-9831-42b1b79738d0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltQueryDirectoryFile routine [Installable File System Drivers], ifsk.fltquerydirectoryfile, fltkernel/FltQueryDirectoryFile, FltQueryDirectoryFile, FltApiRef_p_to_z_d91e48f4-f6a2-4f36-a5f6-9e39821446c2.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows Vista.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltQueryDirectoryFile
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltQueryDirectoryFile function


## -description


The <b>FltQueryDirectoryFile</b> routine returns various kinds of information about files in the directory specified by a given file object.


## -syntax


````
NTSTATUS FltQueryDirectoryFile(
  _In_      PFLT_INSTANCE          Instance,
  _In_      PFILE_OBJECT           FileObject,
  _Out_     PVOID                  FileInformation,
  _In_      ULONG                  Length,
  _In_      FILE_INFORMATION_CLASS FileInformationClass,
  _In_      BOOLEAN                ReturnSingleEntry,
  _In_opt_  PUNICODE_STRING        FileName,
  _In_      BOOLEAN                RestartScan,
  _Out_opt_ PULONG                 LengthReturned
);
````


## -parameters




### -param Instance [in]

Opaque pointer to the minifilter driver instance that initiates the I/O.


### -param FileObject [in]

Pointer to the file object that represents the directory to be scanned.


### -param FileInformation [out]

Pointer to a buffer that receives the desired information about the file. The structure of the information returned in the buffer is defined by the <i>FileInformationClass</i> parameter.


### -param Length [in]

Size, in bytes, of the buffer pointed to by <i>FileInformation</i>. The caller should set this parameter according to the given <i>FileInformationClass</i>.


### -param FileInformationClass [in]

Type of information to be returned about files in the directory. One of the values in the following table can be used.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>FileBothDirectoryInformation</b>

</td>
<td>
Return a FILE_BOTH_DIR_INFORMATION structure for each file.

</td>
</tr>
<tr>
<td>
<b>FileDirectoryInformation</b>

</td>
<td>
Return a FILE_DIRECTORY_INFORMATION structure for each file.

</td>
</tr>
<tr>
<td>
<b>FileFullDirectoryInformation</b>

</td>
<td>
Return a FILE_FULL_DIR_INFORMATION structure for each file.

</td>
</tr>
<tr>
<td>
<b>FileIdBothDirectoryInformation</b>

</td>
<td>
Return a FILE_ID_BOTH_DIR_INFORMATION structure for each file.

</td>
</tr>
<tr>
<td>
<b>FileIdFullDirectoryInformation</b>

</td>
<td>
Return a FILE_ID_FULL_DIR_INFORMATION structure for each file.

</td>
</tr>
<tr>
<td>
<b>FileNamesInformation</b>

</td>
<td>
Return a FILE_NAMES_INFORMATION structure for each file.

</td>
</tr>
<tr>
<td>
<b>FileObjectIdInformation</b>

</td>
<td>
Return a FILE_OBJECTID_INFORMATION structure for each file. This information class is valid only for NTFS volumes starting with Microsoft Windows 2000.

</td>
</tr>
<tr>
<td>
<b>FileReparsePointInformation</b>

</td>
<td>
Return a single FILE_REPARSE_POINT_INFORMATION structure for the directory.

</td>
</tr>
</table>
 


### -param ReturnSingleEntry [in]

Set to <b>TRUE</b> if only a single entry should be returned, <b>FALSE</b> otherwise. If this parameter is <b>TRUE</b>, <b>FltQueryDirectoryFile</b> returns only the first entry that is found.


### -param FileName [in, optional]

Pointer to a caller-allocated Unicode string that contains the name of a file (or multiple files, if wildcards are used) within the directory specified by <i>FileObject</i>. This parameter is optional and can be <b>NULL</b>. 

If <i>FileName</i> is not <b>NULL</b>, only files whose names match the <i>FileName</i> string are included in the directory scan. If <i>FileName</i> is <b>NULL</b>, all files are included. If <i>RestartScan</i> is <b>FALSE</b>, the value of <i>FileName</i> is ignored.


### -param RestartScan [in]

Set to <b>TRUE</b> if the scan is to start at the first entry in the directory. Set to <b>FALSE</b> if resuming the scan from a previous call. The caller must set this parameter to <b>TRUE</b> when calling <b>FltQueryDirectoryFile </b>for the first time.


### -param LengthReturned [out, optional]

Receives the number of bytes actually written to the given <i>FileInformation</i> buffer.


## -returns



<b>FltQueryDirectoryFile </b>returns STATUS_SUCCESS or an appropriate error status. Note that the set of error status values that can be returned is file-system-specific.




## -remarks



<b>FltQueryDirectoryFile </b>returns information about files that are contained in the directory that is represented by <i>FileObject</i>. 

The first call to <b>FltQueryDirectoryFile</b> determines the set of entries to be included in the directory scan for all subsequent calls, based on the values of <i>ReturnSingleEntry</i>, <i>FileName</i>, and <i>RestartScan</i>. If there is at least one matching entry, <b>FltQueryDirectoryFile</b> creates a FILE_<i>XXX</i>_INFORMATION structure (see the above table) for each entry in turn and stores the structure into the buffer. 

Assuming that at least one matching directory entry is found, the number of entries for which information is returned is the smallest of the following: 

<ul>
<li>
 One entry, if <i>ReturnSingleEntry</i> is <b>TRUE</b> and <i>FileName</i> is <b>NULL</b>.  

</li>
<li>
 The number of entries that match the <i>FileName</i> string, if <i>FileName</i> is not <b>NULL</b>. (Note that if the string contains no wildcards, there can be at most one matching entry.)

</li>
<li>
 The number of entries whose information fits into the specified buffer.

</li>
<li>
 The number of entries contained in the directory.

</li>
</ul>
On the first call to <b>FltQueryDirectoryFile</b>, if the structure created for the first entry found too large to fit into the output buffer, only the fixed portion of the structure is returned. The fixed portion consists of all fields of the structure except the final <i>FileName</i> string. On the first call, but not on subsequent ones, the I/O system ensures that the buffer is large enough to hold the fixed portion of the appropriate FILE_<i>XXX</i>_INFORMATION structure. When this happens, <b>FltQueryDirectoryFile</b> returns an appropriate status value such as STATUS_BUFFER_OVERFLOW.  Also on the first call to <b>FltQueryDirectoryFile</b>, if there is no file in the <i>FileObject</i> directory that matches the <i>FileName</i> parameter, <b>FltQueryDirectoryFile</b> returns an appropriate status value such as STATUS_NO_SUCH_FILE.

On each call, <b>FltQueryDirectoryFile</b> returns as many FILE_<i>XXX</i>_INFORMATION structures (one per directory entry) as can be contained entirely in the buffer pointed to by <i>FileInformation</i>. As long as the output buffer contains at least one complete structure, the status value returned is STATUS_SUCCESS. No information about any remaining entries is reported. Thus, except in the cases listed above where only one entry is returned, <b>FltQueryDirectoryFile</b> must be called at least twice to enumerate the contents of an entire directory (for example, when the <i>FileName</i> parameter contains one or more wildcard characters or is <b>NULL</b>). 

The final call to <b>FltQueryDirectoryFile</b> returns an empty output buffer and reports an appropriate status value such as STATUS_NO_MORE_FILES. 


<div class="alert"><b>Note</b>    When <b>FltQueryDirectoryFile</b> is called multiple times on the same directory, it is possible that the number of entries for which information is returned will be less than expected. This is because the set of entries to be included in the directory scan is fixed on the first call to <b>FltQueryDirectoryFile</b>. In subsequent calls, <b>FltQueryDirectoryFile</b> resumes the directory scan wherever it left off in this same enumeration. However, between calls to <b>FltQueryDirectoryFile</b>, the actual directory entries can change so that they are no longer in sync with the original enumeration.</div>
<div> </div>


<b>FltQueryDirectoryFile </b>returns zero in any member of a FILE_<i>XXX</i>_INFORMATION structure that is not supported by the file system. 

For information about other file information query routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545843">File Objects</a>. 

Callers of <b>FltQueryDirectoryFile</b> must be running at IRQL = PASSIVE_LEVEL and with APCs enabled. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543219">Disabling APCs</a>.




## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\ntifs\ns-ntifs-_file_full_dir_information.md">FILE_FULL_DIR_INFORMATION</a>



<a href="..\ntifs\ns-ntifs-_file_directory_information.md">FILE_DIRECTORY_INFORMATION</a>



<a href="..\fltkernel\nf-fltkernel-fltcreatefileex.md">FltCreateFileEx</a>



<a href="..\ntifs\ns-ntifs-_file_id_full_dir_information.md">FILE_ID_FULL_DIR_INFORMATION</a>



<a href="..\ntifs\ns-ntifs-_file_objectid_information.md">FILE_OBJECTID_INFORMATION</a>



<a href="..\ntifs\ns-ntifs-_file_names_information.md">FILE_NAMES_INFORMATION</a>



<a href="..\ntifs\ns-ntifs-_file_reparse_point_information.md">FILE_REPARSE_POINT_INFORMATION</a>



<a href="..\ntifs\ns-ntifs-_file_both_dir_information.md">FILE_BOTH_DIR_INFORMATION</a>



<a href="..\ntifs\nf-ntifs-zwquerydirectoryfile.md">ZwQueryDirectoryFile</a>



<a href="..\ntifs\ns-ntifs-_file_id_both_dir_information.md">FILE_ID_BOTH_DIR_INFORMATION</a>



<a href="..\fltkernel\nf-fltkernel-fltcreatefile.md">FltCreateFile</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltQueryDirectoryFile routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

