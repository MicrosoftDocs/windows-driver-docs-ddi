---
UID: NF:ntifs.FsRtlValidateReparsePointBuffer
title: FsRtlValidateReparsePointBuffer function
author: windows-driver-content
description: The FsRtlValidateReparsePointBuffer routine verifies that the specified reparse point buffer is valid.
old-location: ifsk\fsrtlvalidatereparsepointbuffer.htm
old-project: ifsk
ms.assetid: fb67b116-12f5-4eef-ab05-f2056ccec4e3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , B, F, FsRtlValidateReparsePointBuffer, FsRtlValidateReparsePointBuffer routine [Installable File System Drivers], P, R, V, a, d, e, f, fsrtlref_809c9e16-62b6-4a08-82d5-d6e86e7844ff.xml, i, ifsk.fsrtlvalidatereparsepointbuffer, l, n, ntifs/FsRtlValidateReparsePointBuffer, o, p, r, s, t, u"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating system.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlValidateReparsePointBuffer
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlValidateReparsePointBuffer function


## -description


The <b>FsRtlValidateReparsePointBuffer</b> routine verifies that the specified reparse point buffer is valid.


## -syntax


````
NTSTATUS FsRtlValidateReparsePointBuffer(
  _In_ ULONG                BufferLength,
  _In_ PREPARSE_DATA_BUFFER ReparseBuffer
);
````


## -parameters




### -param BufferLength [in]

The length of the reparse point buffer.


### -param ReparseBuffer [in]

The reparse point buffer to be validated.


## -returns



The<b> FsRtlValidateReparsePointBuffer</b> returns one of the following NTSTATUS values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The buffer is valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_IO_REPARSE_DATA_INVALID</b></dt>
</dl>
</td>
<td width="60%">
The buffer is not valid, such as if the buffer is too long or the length of the buffer and the data length in its header are not consistent.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_IO_REPARSE_TAG_INVALID</b></dt>
</dl>
</td>
<td width="60%">
The buffer has an invalid reparse tag.

</td>
</tr>
</table>
 




## -remarks



For more information about reparse points, see <a href="https://msdn.microsoft.com/6aae70d9-c934-4759-bb26-728b0ac025d1">Reparse Points in a File System Filter Driver</a>.

Reparse tags contain several bits that cannot be set except by system components. For more information, see <a href="http://go.microsoft.com/fwlink/p/?linkid=179582">Reparse Point Tags</a>.




## -see-also

<a href="..\ntifs\ns-ntifs-_reparse_guid_data_buffer.md">REPARSE_GUID_DATA_BUFFER</a>



<a href="..\ntifs\ns-ntifs-_reparse_data_buffer.md">REPARSE_DATA_BUFFER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlValidateReparsePointBuffer routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

