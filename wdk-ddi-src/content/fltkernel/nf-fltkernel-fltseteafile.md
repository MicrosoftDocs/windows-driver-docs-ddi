---
UID: NF:fltkernel.FltSetEaFile
title: FltSetEaFile function
author: windows-driver-content
description: FltSetEaFile sets extended-attribute (EA) values for a file.
old-location: ifsk\fltseteafile.htm
old-project: ifsk
ms.assetid: 06427ef2-43e9-46c1-92e5-ab1b6146cc43
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.fltseteafile, fltkernel/FltSetEaFile, FltSetEaFile, FltApiRef_p_to_z_7e886e7f-a5f4-4a87-9322-7818e31c84af.xml, FltSetEaFile function [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 2000 Update Rollup 1 for SP4, Windows XP SP3, Windows Server 2003 SP1, and later versions of the Windows operating system.
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
-	FltSetEaFile
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltSetEaFile function


## -description


<b>FltSetEaFile</b> sets extended-attribute (EA) values for a file. 


## -syntax


````
NTSTATUS FltSetEaFile(
  _In_ PFLT_INSTANCE Instance,
  _In_ PFILE_OBJECT  FileObject,
  _In_ PVOID         EaBuffer,
  _In_ ULONG         Length
);
````


## -parameters




#### - Instance [in]

Opaque instance pointer for the minifilter driver instance that the SetEa operation is to be sent to. The instance must be attached to the volume where the file resides. 


#### - FileObject [in]

File object pointer for the file. 


#### - EaBuffer [in]

Pointer to a caller-supplied, <a href="..\wdm\ns-wdm-_file_full_ea_information.md">FILE_FULL_EA_INFORMATION</a>-structured input buffer that contains the extended attribute (EA) values to be set. 


#### - Length [in]

Length, in bytes, of the buffer that the <i>EaBuffer</i> parameter points to. 


## -returns


<b>FltSetEaFile</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 
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

<a href="..\wdm\ns-wdm-_file_full_ea_information.md">FILE_FULL_EA_INFORMATION</a>

<a href="..\ntifs\nf-ntifs-iocheckeabuffervalidity.md">IoCheckEaBufferValidity</a>

<a href="..\fltkernel\nf-fltkernel-fltqueryeafile.md">FltQueryEaFile</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltSetEaFile function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

