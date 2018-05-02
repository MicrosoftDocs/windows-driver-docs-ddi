---
UID: NF:wdm.ClfsRemoveLogContainerSet
title: ClfsRemoveLogContainerSet function
author: windows-driver-content
description: The ClfsRemoveLogContainerSet routine atomically removes a set of containers from a CLFS log.
old-location: kernel\clfsremovelogcontainerset.htm
old-project: kernel
ms.assetid: b73a125f-3ab9-4ec6-a154-7b32334e95eb
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: ClfsRemoveLogContainerSet, ClfsRemoveLogContainerSet routine [Kernel-Mode Driver Architecture], Clfs_8455da3b-79fb-4511-8682-e9167620a369.xml, kernel.clfsremovelogcontainerset, wdm/ClfsRemoveLogContainerSet
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Clfs.sys
-	Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
-	ClfsRemoveLogContainerSet
product: Windows
targetos: Windows
req.typenames: 
---

# ClfsRemoveLogContainerSet function


## -description


The <b>ClfsRemoveLogContainerSet</b> routine atomically removes a set of containers from a CLFS log.


## -parameters




### -param plfoLog [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554316">LOG_FILE_OBJECT</a> structure that represents the CLFS log from which the containers will be removed. The caller previously obtained this pointer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff540792">ClfsCreateLogFile</a>. 


### -param cContainers [in]

The number of containers in the set. This is the number of elements in the <i>rgwszContainerPath</i> array.


### -param rgwszContainerPath [in]

A pointer to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structures, each of which supplies the path name for one of the containers to be removed. The number of elements in the array is given by <i>cContainers</i>. A given path can be absolute or relative to the location of the base log file for the CLFS log represented by <i>plfoLog</i>. Paths that are relative to the base log file must begin with CLFS_CONTAINER_RELATIVE_PREFIX, which is the string literal (L"%BLF%\\"). The directories "." and ".." are not allowed in a relative path.


### -param fForce [in]

A Boolean value that specifies whether the container removal is forced (<b>TRUE</b>) or lazy (<b>FALSE</b>).


## -returns



<b>ClfsRemoveLogContainerSet</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h. 




## -remarks



Forced container removal (<i>fForce</i> = <b>TRUE</b>) succeeds only if the containers to be removed are not part of the active log.

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540770">ClfsAddLogContainerSet</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540792">ClfsCreateLogFile</a>



<a href="https://msdn.microsoft.com/5c49bf4f-acc6-4c0f-bbc2-bafb68ea1a74">ClfsRemoveLogContainer </a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554316">LOG_FILE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

