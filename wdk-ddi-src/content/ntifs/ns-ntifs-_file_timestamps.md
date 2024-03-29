---
UID: NS:ntifs._FILE_TIMESTAMPS
title: FILE_TIMESTAMPS (ntifs.h)
description: The FILE_TIMESTAMPS structure specifies the last recorded instance of specific actions on a file.
old-location: ifsk\file_timestamps.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FILE_TIMESTAMPS structure"]
ms.keywords: "*PFILE_TIMESTAMPS, FILE_TIMESTAMPS, FILE_TIMESTAMPS structure [Installable File System Drivers], PFILE_TIMESTAMPS, PFILE_TIMESTAMPS structure pointer [Installable File System Drivers], _FILE_TIMESTAMPS, ifsk.file_timestamps, ntifs/File_TIMESTAMPS, ntifs/PFILE_TIMESTAMPS"
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: FILE_TIMESTAMPS, *PFILE_TIMESTAMPS
f1_keywords:
 - _FILE_TIMESTAMPS
 - ntifs/_FILE_TIMESTAMPS
 - PFILE_TIMESTAMPS
 - ntifs/PFILE_TIMESTAMPS
 - FILE_TIMESTAMPS
 - ntifs/FILE_TIMESTAMPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FILE_TIMESTAMPS
 - PFILE_TIMESTAMPS
 - FILE_TIMESTAMPS
---

# _FILE_TIMESTAMPS structure

## -description

The **FILE_TIMESTAMPS** structure specifies the last recorded instance of specific actions on a file.

## -struct-fields

### -field CreationTime

Specifies the creation time of a file.

### -field LastAccessTime

Specifies the last time a file was accessed.

### -field LastWriteTime

Specifies the last time a file was written to.

### -field ChangeTime

Specifies the last time a file was changed or modified.

## -see-also

[**ATOMIC_CREATE_ECP_CONTEXT**](/previous-versions/mt734230(v=vs.85))
