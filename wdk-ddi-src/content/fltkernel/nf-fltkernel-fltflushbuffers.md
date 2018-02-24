---
UID: NF:fltkernel.FltFlushBuffers
title: FltFlushBuffers function
author: windows-driver-content
description: The FltFlushBuffers routine is used by the minifilter driver to send a flush request for a given file to the file system.
old-location: ifsk\fltflushbuffers.htm
old-project: ifsk
ms.assetid: 269be3a9-7dd8-45e2-8687-99f8ca8f9b8b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ifsk.fltflushbuffers, FltApiRef_e_to_o_cd194ce5-6afd-49f2-84c5-aa93ede9309a.xml, fltkernel/FltFlushBuffers, FltFlushBuffers routine [Installable File System Drivers], FltFlushBuffers
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
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	FltMgr.lib
-	FltMgr.dll
apiname:
-	FltFlushBuffers
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltFlushBuffers function


## -description


The <b>FltFlushBuffers</b> routine is used by the minifilter driver to send a flush request for a given file to the file system. 


## -syntax


````
NTSTATUS FltFlushBuffers(
  _In_ PFLT_INSTANCE Instance,
  _In_ PFILE_OBJECT  FileObject
);
````


## -parameters




### -param Instance [in]

Opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


### -param FileObject [in]

File object pointer for the file. This parameter is required and cannot be <b>NULL</b>. 


## -returns



<b>FltFlushBuffers</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_MEDIA_WRITE_PROTECTED</b></dt>
</dl>
</td>
<td width="60%">
The file resides on a write-protected volume. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_VOLUME_DISMOUNTED</b></dt>
</dl>
</td>
<td width="60%">
The file resides on a volume that is not currently mounted. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



A minifilter driver can call <b>FltFlushBuffers</b> to issue an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549235">IRP_MJ_FLUSH_BUFFERS</a> request to the file system for a given file. The flush operation is synchronous and is issued to the instance(s) below the specified instance. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549235">IRP_MJ_FLUSH_BUFFERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltFlushBuffers routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

