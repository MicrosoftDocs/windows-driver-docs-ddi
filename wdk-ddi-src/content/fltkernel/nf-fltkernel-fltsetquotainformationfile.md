---
UID: NF:fltkernel.FltSetQuotaInformationFile
title: FltSetQuotaInformationFile function
author: windows-driver-content
description: The FltSetQuotaInformationFile routine modifies quota entries for a file object.
old-location: ifsk\fltsetquotainformationfile.htm
old-project: ifsk
ms.assetid: 89EC9F5C-24AE-4340-99CF-05323F99B465
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltSetQuotaInformationFile function [Installable File System Drivers], fltkernel/FltSetQuotaInformationFile, ifsk.fltsetquotainformationfile, FltSetQuotaInformationFile
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltSetQuotaInformationFile
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltSetQuotaInformationFile function


## -description


The <b>FltSetQuotaInformationFile</b> routine modifies quota entries for a file object. 


## -syntax


````
NTSTATUS FltSetQuotaInformationFile(
  _In_ PFLT_INSTANCE Instance,
  _In_ PFILE_OBJECT  FileObject,
  _In_ PVOID         Buffer,
  _In_ ULONG         Length
);
````


## -parameters




### -param Instance [in]

An opaque instance pointer for the minifilter driver instance that the operation is to be sent to. The instance must be attached to the volume where the file resides. 


### -param FileObject [in]

The file object pointer for the file. 


### -param Buffer [in]

A pointer to a caller-supplied, <a href="..\ntifs\ns-ntifs-_file_get_quota_information.md">FILE_GET_QUOTA_INFORMATION</a>-structured input buffer that contains the quota information entries to be set. 


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

<a href="..\ntifs\ns-ntifs-_file_get_quota_information.md">FILE_GET_QUOTA_INFORMATION</a>



<a href="..\ntifs\nf-ntifs-zwsetquotainformationfile.md">ZwSetQuotaInformationFile</a>



<a href="..\fltkernel\nf-fltkernel-fltqueryquotainformationfile.md">FltQueryQuotaInformationFile</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltSetQuotaInformationFile function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

