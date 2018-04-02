---
UID: NF:wdm.ClfsAddLogContainer
title: ClfsAddLogContainer function
author: windows-driver-content
description: The ClfsAddLogContainer routine adds a container to a CLFS log.
old-location: kernel\clfsaddlogcontainer.htm
old-project: kernel
ms.assetid: 05ab9817-3f49-4ab5-b35d-1c89f5fe6e44
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: ClfsAddLogContainer, ClfsAddLogContainer routine [Kernel-Mode Driver Architecture], Clfs_30478f90-41d2-4a83-8291-83b90601dc11.xml, kernel.clfsaddlogcontainer, wdm/ClfsAddLogContainer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
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
-	ClfsAddLogContainer
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ClfsAddLogContainer function


## -description


The <b>ClfsAddLogContainer</b> routine adds a container to a CLFS log.


## -parameters




### -param plfoLog [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554316">LOG_FILE_OBJECT</a> structure that represents the log to which the container will be added. The caller previously obtained this pointer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff540792">ClfsCreateLogFile</a>.


### -param pcbContainer [in]

A pointer to a ULONGLONG-typed variable. The role of this parameter depends on whether the log currently has at least one container.

<ul>
<li>
If the log currently has no containers, the caller supplies a positive integer that is the requested size, in bytes, of the new container. CLFS creates a container that is the requested size rounded up to a multiple of 512KB (for a dedicated log) or 1MB (for a multiplexed log).

</li>
<li>
If the log currently has at least one container and this parameter is the <b>NULL</b> pointer, CLFS creates a new container that is the same size as the existing containers. (All containers in a log must be the same size.)

</li>
<li>
If the log currently has at least one container and this parameter is a valid pointer, the caller supplies a positive integer that is the requested size, in bytes, of the new container. The requested size is rounded up to a multiple of 512KB (for a dedicated log) or 1MB (for a multiplexed log). If the rounded-up size is at least as large as the existing container size, CLFS creates a new container that is the same size as the existing containers. On successful return, this parameter receives the existing container size. If the rounded-up size is less than the existing container size, <b>ClfsAddLogContainer</b> fails.

</li>
</ul>

### -param puszContainerPath [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that supplies the path name for the new container. The path can be absolute or relative to the location of the base log file. Paths that are relative to the base log file must begin with CLFS_CONTAINER_RELATIVE_PREFIX, which is the string literal (L"%BLF%\\").


## -returns



<b>ClfsAddLogContainer</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



A container is a contiguous extent on stable storage. For example, a container could be a contiguous file on disk. A log is a set of containers along with a base log file. For more information about containers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541862">CLFS Stable Storage</a>. 

A container specified by a path that is relative to the base log file must be in the same directory as the base log file or a subdirectory of the base log file. The directories "." and ".." are not allowed in a relative path.

A log can have some containers with absolute paths and other containers with relative paths.

Containers are created in a non-compressed mode and are initialized with zeros.

A log must have at least two containers before any I/O can be performed on it.

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540770">ClfsAddLogContainerSet</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541715">ClfsRemoveLogContainer</a>
 

 

