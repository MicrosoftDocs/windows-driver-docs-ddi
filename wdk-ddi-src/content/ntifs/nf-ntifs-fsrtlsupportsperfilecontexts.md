---
UID: NF:ntifs.FsRtlSupportsPerFileContexts
title: FsRtlSupportsPerFileContexts macro (ntifs.h)
description: The FsRtlSupportsPerFileContexts macro checks if per file context information is supported by the file system that is associated with a specified FILE_OBJECT.
old-location: ifsk\fsrtlsupportsperfilecontexts.htm
tech.root: ifsk
ms.assetid: 28f0e98f-1f7b-4dcf-8151-e13981634617
ms.date: 04/16/2018
keywords: ["FsRtlSupportsPerFileContexts macro"]
ms.keywords: FsRtlSupportsPerFileContexts, FsRtlSupportsPerFileContexts , FsRtlSupportsPerFileContexts function [Installable File System Drivers], fsrtlref_98e99a7a-c80d-43d5-a0f6-3eea35a8d20a.xml, ifsk.fsrtlsupportsperfilecontexts, ntifs/FsRtlSupportsPerFileContexts
f1_keywords:
 - "ntifs/FsRtlSupportsPerFileContexts"
 - "FsRtlSupportsPerFileContexts"
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: Any
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntifs.h
api_name:
- FsRtlSupportsPerFileContexts
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlSupportsPerFileContexts macro


## -description


The <b>FsRtlSupportsPerFileContexts</b> macro checks if per file context information is supported by the file system that is associated with a specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">FILE_OBJECT</a>.


## -parameters




### -param _fo

<p>A FILE_OBJECT that is associated with the file system to be checked.</p>






## -remarks



None




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">FILE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/tracking-per-file-context-in-a-legacy-file-system-filter-driver">Tracking Per-File Context in a Legacy File System Filter Driver</a>
 

 

