---
UID: NS:ntifs._FILE_PIPE_REMOTE_INFORMATION
title: _FILE_PIPE_REMOTE_INFORMATION
author: windows-driver-content
description: The FILE_PIPE_REMOTE_INFORMATION structure contains information about the remote end of a named pipe.
old-location: ifsk\file_pipe_remote_information.htm
old-project: ifsk
ms.assetid: e0e62227-5e84-45bd-9127-f5bbb30ba6f3
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _FILE_PIPE_REMOTE_INFORMATION, FILE_PIPE_REMOTE_INFORMATION, *PFILE_PIPE_REMOTE_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FILE_PIPE_REMOTE_INFORMATION
req.alt-loc: ntifs.h
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
req.typenames: FILE_PIPE_REMOTE_INFORMATION, *PFILE_PIPE_REMOTE_INFORMATION
---

# _FILE_PIPE_REMOTE_INFORMATION structure



## -description
The <b>FILE_PIPE_REMOTE_INFORMATION</b> structure contains information about the remote end of a named pipe.



## -syntax

````
typedef struct _FILE_PIPE_REMOTE_INFORMATION {
  LARGE_INTEGER CollectDataTime;
  ULONG         MaximumCollectionCount;
} FILE_PIPE_REMOTE_INFORMATION, *PFILE_PIPE_REMOTE_INFORMATION;
````


## -struct-fields

### -field CollectDataTime

The maximum amount of time, in 100-nanosecond intervals, that elapses before transmission of data from the client machine to the server.


### -field MaximumCollectionCount

The maximum size, in bytes, of data that will be collected on the client machine before transmission to the server.


## -remarks
Remote information is not available for local pipes or for the server end of a remote pipe.

For information about pipes, see <a href="https://msdn.microsoft.com/7cb8cbe4-eec8-4dda-9cb7-8d37abcee6f4">Pipes</a>.</p>