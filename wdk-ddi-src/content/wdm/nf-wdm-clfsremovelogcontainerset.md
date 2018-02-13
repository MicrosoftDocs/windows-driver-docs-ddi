---
UID: NF:wdm.ClfsRemoveLogContainerSet
title: ClfsRemoveLogContainerSet function
author: windows-driver-content
description: The ClfsRemoveLogContainerSet routine atomically removes a set of containers from a CLFS log.
old-location: kernel\clfsremovelogcontainerset.htm
old-project: kernel
ms.assetid: b73a125f-3ab9-4ec6-a154-7b32334e95eb
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/ClfsRemoveLogContainerSet, ClfsRemoveLogContainerSet, ClfsRemoveLogContainerSet routine [Kernel-Mode Driver Architecture], Clfs_8455da3b-79fb-4511-8682-e9167620a369.xml, kernel.clfsremovelogcontainerset
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
-	ClfsRemoveLogContainerSet
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ClfsRemoveLogContainerSet function


## -description


The <b>ClfsRemoveLogContainerSet</b> routine atomically removes a set of containers from a CLFS log.


## -syntax


````
NTSTATUS ClfsRemoveLogContainerSet(
  _In_ PLOG_FILE_OBJECT plfoLog,
  _In_ USHORT           cContainers,
  _In_ PUNICODE_STRING  rgwszContainerPath,
  _In_ BOOLEAN          fForce
);
````


## -parameters




### -param plfoLog [in]

A pointer to a <a href="..\wdm\ns-wdm-_file_object.md">LOG_FILE_OBJECT</a> structure that represents the CLFS log from which the containers will be removed. The caller previously obtained this pointer by calling <a href="..\wdm\nf-wdm-clfscreatelogfile.md">ClfsCreateLogFile</a>. 


### -param cContainers [in]

The number of containers in the set. This is the number of elements in the <i>rgwszContainerPath</i> array.


### -param rgwszContainerPath [in]

A pointer to an array of <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structures, each of which supplies the path name for one of the containers to be removed. The number of elements in the array is given by <i>cContainers</i>. A given path can be absolute or relative to the location of the base log file for the CLFS log represented by <i>plfoLog</i>. Paths that are relative to the base log file must begin with CLFS_CONTAINER_RELATIVE_PREFIX, which is the string literal (L"%BLF%\\"). The directories "." and ".." are not allowed in a relative path.


### -param fForce [in]

A Boolean value that specifies whether the container removal is forced (<b>TRUE</b>) or lazy (<b>FALSE</b>).


## -returns



<b>ClfsRemoveLogContainerSet</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h. 




## -remarks



Forced container removal (<i>fForce</i> = <b>TRUE</b>) succeeds only if the containers to be removed are not part of the active log.

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. 




## -see-also

<a href="..\wdm\ns-wdm-_file_object.md">LOG_FILE_OBJECT</a>



<a href="..\wdm\nf-wdm-clfsremovelogcontainer.md">ClfsRemoveLogContainer </a>



<a href="..\wdm\nf-wdm-clfscreatelogfile.md">ClfsCreateLogFile</a>



<a href="..\wdm\nf-wdm-clfsaddlogcontainerset.md">ClfsAddLogContainerSet</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsRemoveLogContainerSet routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

