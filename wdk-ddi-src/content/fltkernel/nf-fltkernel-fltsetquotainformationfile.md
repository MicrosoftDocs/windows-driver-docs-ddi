---
UID: NF:fltkernel.FltSetQuotaInformationFile
title: FltSetQuotaInformationFile function (fltkernel.h)
description: The FltSetQuotaInformationFile routine modifies quota entries for a file object.
old-location: ifsk\fltsetquotainformationfile.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltSetQuotaInformationFile function"]
ms.keywords: FltSetQuotaInformationFile, FltSetQuotaInformationFile function [Installable File System Drivers], fltkernel/FltSetQuotaInformationFile, ifsk.fltsetquotainformationfile
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
targetos: Windows
req.typenames: 
f1_keywords:
 - FltSetQuotaInformationFile
 - fltkernel/FltSetQuotaInformationFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltSetQuotaInformationFile
---

# FltSetQuotaInformationFile function


## -description

The <b>FltSetQuotaInformationFile</b> routine modifies quota entries for a file object.

## -parameters

### -param Instance [in]


An opaque instance pointer for the minifilter driver instance that the operation is to be sent to. The instance must be attached to the volume where the file resides.

### -param FileObject [in]


The file object pointer for the file.

### -param Buffer [in]


A pointer to a caller-supplied, <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_get_quota_information">FILE_GET_QUOTA_INFORMATION</a>-structured input buffer that contains the quota information entries to be set.

### -param Length [in]


The length, in bytes, of the buffer that the <i>Buffer</i> parameter points to.

## -returns

<b>FltSetQuotaInformationFile</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following. 

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

<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_get_quota_information">FILE_GET_QUOTA_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryquotainformationfile">FltQueryQuotaInformationFile</a>



<a href="/previous-versions/ff567105(v=vs.85)">ZwSetQuotaInformationFile</a>
