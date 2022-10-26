---
UID: NF:dbgeng.IDebugClient8.OpenDumpFileWide2
title: IDebugClient8::OpenDumpFileWide2 (dbgeng.h)
description: The OpenDumpFileWide2 
old-location: debugger\idebugclient8_OpenDumpFileWide2.htm
tech.root: debugger
ms.date: 10/26/2022
keywords: ["IDebugClient8::OpenDumpFileWide2"]
ms.keywords: IDebugClient8 interface [Windows Debugging],OpenDumpFileWide2 method, IDebugClient8.OpenDumpFileWide2, IDebugClient8::OpenDumpFileWide2, OpenDumpFileWide2, OpenDumpFileWide2 method [Windows Debugging], OpenDumpFileWide2 method [Windows Debugging],IDebugClient8 interface, dbgeng/IDebugClient8::OpenDumpFileWide2, debugger.idebugclient8_OpenDumpFileWide2
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
req.typenames: 
f1_keywords:
 - IDebugClient8::OpenDumpFileWide2
 - dbgeng/IDebugClient8::OpenDumpFileWide2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient8::OpenDumpFileWide2
---

# IDebugClient8::OpenDumpFileWide2


## -description

The <b>OpenDumpFileWide2</b> method opens a dump file as a debugger target.

## -parameters


### -param FileName [in, optional]

Specifies the name of the dump file to open -- unless <i>FileHandle</i> is not zero, in which case <i>FileName</i> is used only when the engine is queried for the name of the dump file.  <i>FileName</i> must include the file name extension.  <i>FileName</i> can include a relative or absolute path; relative paths are relative to the directory in which the debugger was started.  <i>FileName</i> can also be in the form of a file URL, starting with "file://".  If <i>FileName</i> specifies a cabinet (.cab) file, the cabinet file is searched for the first file with extension .kdmp, then .hdmp, then .mdmp, and finally .dmp.

### -param FileHandle [in]

Specifies the file handle of the dump file to open.  If <i>FileHandle</i> is zero, <i>FileName</i> is used to open the dump file.  Otherwise, if <i>FileName</i> is not <b>NULL</b>, the engine returns it when queried for the name of the dump file.  If <i>FileHandle</i> is not zero and <i>FileName</i> is <b>NULL</b>, the engine will return <b>HandleOnly</b> for the file name.

### -param FileHandle [in]

Specifies the The AlternateArch argument which is an IMAGE_FILE_MACHINE_* constant. For more information, see [Image File Machine Constants](/windows/win32/sysinfo/image-file-machine-constants).

This parameter is only relevant if you are using OpenDumpFileWide2 to open an image file (not a dump file) which can be mapped into different architectures. For example ARM64X, where the DLL can be loaded into an x64/EC process or an ARM64 process. 

By default, information about the DLL is presented using whatever architecture the image headers have defined.  If you call OpenDumpFileWide2 with a different architecture, the information will be presented using the the architecture that was passed.  This allows you to see the “fixups” which the OS would have applied if the DLL were loaded into that architecture of process.

For more information about ARM64X, see [Arm64X PE files](/windows/arm/arm64x-pe).

## -returns

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

## -remarks 

The engine doesn't completely attach to the dump file until the WaitForEvent method has been called. When a dump file is created from a process or kernel, information about the last event is stored in the dump file. After the dump file is opened, the next time execution is attempted, the engine will generate this event for the event callbacks. Only then does the dump file become available in the debugging session.
 
For more information about crash dump files, see [Dump-File Targets](/windows-hardware/drivers/debugger/dump-file-targets).


## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_client_context">DEBUG_CLIENT_CONTEXT</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient8">IDebugClient8</a>

