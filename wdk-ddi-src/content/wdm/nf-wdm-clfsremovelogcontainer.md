---
UID: NF:wdm.ClfsRemoveLogContainer
title: ClfsRemoveLogContainer function (wdm.h)
description: The ClfsRemoveLogContainer routine removes a container from a CLFS log.
old-location: kernel\clfsremovelogcontainer.htm
tech.root: kernel
ms.assetid: 5c49bf4f-acc6-4c0f-bbc2-bafb68ea1a74
ms.date: 04/30/2018
keywords: ["ClfsRemoveLogContainer function"]
ms.keywords: ClfsRemoveLogContainer, ClfsRemoveLogContainer routine [Kernel-Mode Driver Architecture], Clfs_f797d534-9c7e-4871-81d1-aff9ccedccf5.xml, kernel.clfsremovelogcontainer, wdm/ClfsRemoveLogContainer
f1_keywords:
 - "wdm/ClfsRemoveLogContainer"
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
- ClfsRemoveLogContainer
product:
- Windows
targetos: Windows
req.typenames: 
---

# ClfsRemoveLogContainer function


## -description


The <b>ClfsRemoveLogContainer</b> routine removes a container from a CLFS log.


## -parameters




### -param plfoLog [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">LOG_FILE_OBJECT</a> structure that represents a CLFS log from which the container will be removed. The caller previously obtained this pointer by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatelogfile">ClfsCreateLogFile</a>.


### -param puszContainerPath [in]

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that supplies the path name for the container to be removed. The path name was created in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsaddlogcontainer">ClfsAddLogContainer</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsaddlogcontainerset">ClfsAddLogContainerSet</a>. The path can be absolute or relative to the location of the base log file for the CLFS log that is represented by <i>plfoLog</i>. Paths that are relative to the base log file must begin with CLFS_CONTAINER_RELATIVE_PREFIX, which is the string literal (L"%BLF%\\"). The directories "." and ".." are not allowed in a relative path.


### -param fForce [in]

A Boolean value that specifies whether the container removal is forced (<b>TRUE</b>) or lazy (<b>FALSE</b>).


## -returns



<b>ClfsRemoveLogContainer</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h. 




## -remarks



Forced container removal (<i>fForce</i> = <b>TRUE</b>) succeeds only if the container to be removed is not part of the active log.

For an explanation of CLFS concepts and terminology, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-common-log-file-system">Common Log File System</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsaddlogcontainer">ClfsAddLogContainer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsaddlogcontainerset">ClfsAddLogContainerSet</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatelogfile">ClfsCreateLogFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsremovelogcontainerset">ClfsRemoveLogContainerSet </a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">LOG_FILE_OBJECT</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

