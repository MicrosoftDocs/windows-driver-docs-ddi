---
UID: NF:wdm.ClfsAddLogContainerSet
title: ClfsAddLogContainerSet function (wdm.h)
description: The ClfsAddLogContainerSet routine atomically adds a set of containers to a CLFS log.
old-location: kernel\clfsaddlogcontainerset.htm
tech.root: kernel
ms.assetid: 252dc455-e2d9-40db-83ea-a53e5ff8eda0
ms.date: 04/30/2018
keywords: ["ClfsAddLogContainerSet function"]
ms.keywords: ClfsAddLogContainerSet, ClfsAddLogContainerSet routine [Kernel-Mode Driver Architecture], Clfs_f112becb-a913-4d1a-8e58-d7365468be18.xml, kernel.clfsaddlogcontainerset, wdm/ClfsAddLogContainerSet
f1_keywords:
 - "wdm/ClfsAddLogContainerSet"
 - "ClfsAddLogContainerSet"
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Clfs.sys
- Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
- ClfsAddLogContainerSet
targetos: Windows
req.typenames: 
---

# ClfsAddLogContainerSet function


## -description


The <b>ClfsAddLogContainerSet</b> routine atomically adds a set of containers to a CLFS log.


## -parameters




### -param plfoLog 
[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">LOG_FILE_OBJECT</a> structure that represents the log to which the containers will be added. The caller previously obtained this pointer by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatelogfile">ClfsCreateLogFile</a>.


### -param cContainers 
[in]
The number of containers in the set. This is the number of elements in the <i>rguszContainerPath</i> array.


### -param pcbContainer 
[in, optional]
A pointer to a ULONGLONG-typed variable. The role of this parameter depends on whether the log currently has at least one container.

<ul>
<li>
If the log currently has no containers, the caller supplies a positive integer that is the requested size, in bytes, of an individual container. CLFS creates containers that are the requested size rounded up to a multiple of 512KB (for a dedicated log) or 1MB (for a multiplexed log). 

</li>
<li>
If the log currently has at least one container and this parameter is the <b>NULL</b> pointer, CLFS creates new containers that are the same size as the existing containers. (All containers in a log must be the same size.)

</li>
<li>
If the log currently has at least one container and this parameter is a valid pointer, the caller supplies a positive integer that is the requested size, in bytes, of an individual container. The requested size is rounded up to a multiple of 512KB (for a dedicated log) or 1MB (for a shared log). If the rounded-up size is at least as large as the existing container size, CLFS creates new containers that are the same size as the existing containers. On successful return, this parameter receives the existing container size. If the rounded-up size is less than the existing container size, <b>ClfsAddLogContainerSet</b> fails. 

</li>
</ul>

### -param rguszContainerPath 
[in]
A pointer to an array of <a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structures. Each string supplies the path name for one of the new containers. The number of elements in the array is given by <i>cContainers</i>. A given path can be absolute or relative to the location of the base log file. Paths that are relative to the base log file must begin with CLFS_CONTAINER_RELATIVE_PREFIX, which is the string literal (L"%BLF%\\").


## -returns



<b>ClfsAddLogContainer</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



A container is a contiguous extent on stable storage. For example, a container could be a contiguous file on disk. A log is a set of containers along with a base log file. For more information about containers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/clfs-stable-storage">CLFS Stable Storage</a>. 

A container specified by a path that is relative to the base log file must be in the same directory as the base log file or a subdirectory of the base log file. The directories "." and ".." are not allowed in a relative path.

A log can have some containers with absolute paths and other containers with relative paths.

Containers are created in a non-compressed mode and are initialized with zeros.

A log must have at least two containers before any I/O can be performed on it.

For an explanation of CLFS concepts and terminology, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-common-log-file-system">Common Log File System</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsaddlogcontainer">ClfsAddLogContainer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsremovelogcontainerset">ClfsRemoveLogContainerSet</a>
 

 

