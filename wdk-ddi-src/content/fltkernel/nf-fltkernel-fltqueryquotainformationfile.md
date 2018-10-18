---
UID: NF:fltkernel.FltQueryQuotaInformationFile
title: FltQueryQuotaInformationFile function
author: windows-driver-content
description: The FltQueryQuotaInformationFile routine retrieves quota entries associated with a file object.
old-location: ifsk\fltqueryquotainformationfile.htm
tech.root: ifsk
ms.assetid: B460BE83-7050-469A-9AD6-68A47F03EB4B
ms.date: 4/16/2018
ms.keywords: FltQueryQuotaInformationFile, FltQueryQuotaInformationFile function [Installable File System Drivers], fltkernel/FltQueryQuotaInformationFile, ifsk.fltqueryquotainformationfile
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows 8.
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
-	FltQueryQuotaInformationFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltQueryQuotaInformationFile function


## -description


The <b>FltQueryQuotaInformationFile</b> routine retrieves quota entries associated with a file object.


## -parameters




### -param Instance [in]

An opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


### -param FileObject [in]

A file object pointer for an open file, directory, storage device, or volume. This parameter is required and cannot be <b>NULL</b>. 


### -param IoStatusBlock [out]

A caller-supplied <b>IO_STATUS_BLOCK</b> to receive the result of the call to <b>FltQueryQuotaInformationFile</b>. If the call  fails because of an invalid <b>SID</b> list, the <b>Information</b> field will contain the location in <i>SidList</i> where the error occurred.


### -param Buffer [out]

A pointer to a caller-supplied <a href="https://msdn.microsoft.com/2abaf505-b890-43b6-a277-d930417bdcb8"> FILE_GET_QUOTA_INFORMATION</a>-structured input buffer where the quota information values are to be returned. 


### -param Length [in]

The length, in bytes, of the buffer that the <i>Buffer</i> parameter points to. 


### -param ReturnSingleEntry [in]

Set to <b>TRUE</b> if <b>FltQueryQuotaInformationFile</b> should return only the first entry that is found. 


### -param SidList [in, optional]

A pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff540298">FILE_GET_QUOTA_INFORMATION</a>-structured input buffer that specifies the quota information to be queried. This parameter is optional and can be <b>NULL</b>. 


### -param SidListLength [in]

The length, in bytes, of the buffer that the <i>SidList</i> parameter points to. 


### -param StartSid [in, optional]

The index of the entry at which to begin scanning the file's quota information list. This parameter is ignored if the <i>SidList</i> parameter points to a nonempty list. This parameter is optional and can be <b>NULL</b>. 


### -param RestartScan [in]

Set to <b>TRUE</b> if <b>FltQueryQuotaInformationFile</b> should begin the scan at the first entry in the file's quota information list. If this parameter is not set to <b>TRUE</b>, the scan is resumed from a previous call to <b>FltQueryQuotaInformationFile</b>. 


### -param LengthReturned [out, optional]

A pointer to a caller-allocated variable that receives the size, in bytes, of the information returned in <i>Buffer</i>. This parameter is optional and can be <b>NULL</b>. 


## -returns



<b>FltQueryQuotaInformationFile</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following. 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
The instance or volume is being torn down. This is an error code. 

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540298">FILE_GET_QUOTA_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451042">FltSetQuotaInformationFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567064">ZwQueryQuotaInformationFile</a>
 

 

