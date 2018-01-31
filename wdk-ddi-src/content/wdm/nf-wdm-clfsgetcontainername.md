---
UID: NF:wdm.ClfsGetContainerName
title: ClfsGetContainerName function
author: windows-driver-content
description: The ClfsGetContainerName routine returns the path name of a specified container.
old-location: kernel\clfsgetcontainername.htm
old-project: kernel
ms.assetid: 727b2e29-9e2d-4386-a30b-5727e1261fad
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.clfsgetcontainername, Clfs_dce31248-386b-4f6d-8e88-55ef9d70fe84.xml, wdm/ClfsGetContainerName, ClfsGetContainerName, ClfsGetContainerName routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
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
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Clfs.sys
-	Ext-MS-Win-fs-clfs-l1-1-0.dll
apiname:
-	ClfsGetContainerName
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ClfsGetContainerName function


## -description


The <b>ClfsGetContainerName</b> routine returns the path name of a specified container.


## -syntax


````
NTSTATUS ClfsGetContainerName(
  _In_      PLOG_FILE_OBJECT  plfoLog,
  _In_      CLFS_CONTAINER_ID cidLogicalContainer,
  _Out_     PUNICODE_STRING   puszContainerName,
  _Out_opt_ PULONG            pcActualLenContainerName
);
````


## -parameters




#### - plfoLog [in]

A pointer to a <a href="..\wdm\ns-wdm-_file_object.md">LOG_FILE_OBJECT</a> structure that represents a CLFS log. The caller previously obtained this pointer by calling <a href="..\wdm\nf-wdm-clfscreatelogfile.md">ClfsCreateLogFile</a>.


#### - cidLogicalContainer [in]

The logical identifier of a container in the CLFS log.


#### - puszContainerName [out]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure. The <b>Buffer</b> member of <i>puszContainerName</i> must point to a caller-allocated buffer that receives the path name of the container. The <b>MaximumLength</b> member must supply the size of the buffer.


#### - pcActualLenContainerName [out, optional]

A pointer to a ULONG-typed variable that receives the actual length, in Unicode characters, of the container's path name. This parameter can be <b>NULL</b>.


## -returns


<b>ClfsGetContainerName</b> returns one of the status codes defined in Ntstatus.h. The following table gives the meanings of various return values.
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
The <b>Buffer</b> member of <i>puszContainerName</i> receives the full path name of the container. If <i>pcActualLenContainerName</i> is not <b>NULL</b>, it receives the actual length, in Unicode characters, of the full path name.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The actual length, in Unicode characters, of the full path name is larger than <i>puszContainerName</i>-&gt;<b>MaximumLength</b>. The <b>Buffer</b> member of <i>puszContainerName</i> receives the full path name of the container truncated to the number of characters specified by <i>puszContainerName</i>-&gt;<b>MaximumLength</b>. If <i>pcActualLenContainerName</i> is not <b>NULL</b>, it receives the actual length, in Unicode characters, of the full path name. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other</b></dt>
</dl>
</td>
<td width="60%">
On return, the contents of <i>puszContainerName</i>-&gt;<b>Buffer</b> and <i>pcActualLenContainerName</i> are undefined.

</td>
</tr>
</table> 



## -remarks


For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. 



## -see-also

<a href="..\wdm\nf-wdm-clfsremovelogcontainer.md">ClfsRemoveLogContainer</a>

<a href="..\wdm\nf-wdm-clfsaddlogcontainer.md">ClfsAddLogContainer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsGetContainerName routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

