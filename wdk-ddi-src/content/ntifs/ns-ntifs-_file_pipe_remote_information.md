---
UID: NS:ntifs._FILE_PIPE_REMOTE_INFORMATION
title: _FILE_PIPE_REMOTE_INFORMATION (ntifs.h)
description: The FILE_PIPE_REMOTE_INFORMATION structure contains information about the remote end of a named pipe.
old-location: ifsk\file_pipe_remote_information.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FILE_PIPE_REMOTE_INFORMATION structure"]
ms.keywords: "*PFILE_PIPE_REMOTE_INFORMATION, FILE_PIPE_REMOTE_INFORMATION, FILE_PIPE_REMOTE_INFORMATION structure [Installable File System Drivers], PFILE_PIPE_REMOTE_INFORMATION, PFILE_PIPE_REMOTE_INFORMATION structure pointer [Installable File System Drivers], _FILE_PIPE_REMOTE_INFORMATION, ifsk.file_pipe_remote_information, ntifs/FILE_PIPE_REMOTE_INFORMATION, ntifs/PFILE_PIPE_REMOTE_INFORMATION"
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Windows 2000
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
req.typenames: FILE_PIPE_REMOTE_INFORMATION, *PFILE_PIPE_REMOTE_INFORMATION
f1_keywords:
 - _FILE_PIPE_REMOTE_INFORMATION
 - ntifs/_FILE_PIPE_REMOTE_INFORMATION
 - PFILE_PIPE_REMOTE_INFORMATION
 - ntifs/PFILE_PIPE_REMOTE_INFORMATION
 - FILE_PIPE_REMOTE_INFORMATION
 - ntifs/FILE_PIPE_REMOTE_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FILE_PIPE_REMOTE_INFORMATION
 - PFILE_PIPE_REMOTE_INFORMATION
 - FILE_PIPE_REMOTE_INFORMATION
---

# _FILE_PIPE_REMOTE_INFORMATION structure


## -description

The <b>FILE_PIPE_REMOTE_INFORMATION</b> structure contains information about the remote end of a named pipe.

## -struct-fields

### -field CollectDataTime

The maximum amount of time, in 100-nanosecond intervals, that elapses before transmission of data from the client machine to the server.

### -field MaximumCollectionCount

The maximum size, in bytes, of data that will be collected on the client machine before transmission to the server.

## -remarks

Remote information is not available for local pipes or for the server end of a remote pipe.

For information about pipes, see <a href="/windows/desktop/ipc/pipes">Pipes</a>.

