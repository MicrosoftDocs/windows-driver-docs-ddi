---
UID: NF:dbgeng.IDebugEventCallbacksWide.CreateProcess
title: IDebugEventCallbacksWide::CreateProcess
description: The CreateProcess callback method is called by the engine when a create-processdebugging event occurs in the target.
old-location: debugger\idebugeventcallbackswide_createprocess.htm
tech.root: debugger
ms.assetid: d5378b35-da27-419f-a161-0c542aa4a9f9
ms.date: 05/03/2018
ms.keywords: CreateProcess, CreateProcess method [Windows Debugging], CreateProcess method [Windows Debugging],IDebugEventCallbacksWide interface, IDebugEventCallbacksWide interface [Windows Debugging],CreateProcess method, IDebugEventCallbacksWide.CreateProcess, IDebugEventCallbacksWide::CreateProcess, dbgeng/IDebugEventCallbacksWide::CreateProcess, debugger.idebugeventcallbackswide_createprocess
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugEventCallbacksWide.CreateProcess
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugEventCallbacksWide::CreateProcess


## -description


The <b>CreateProcess</b> callback method is called by the engine when a create-processdebugging event occurs in the target.


## -parameters




### -param ImageFileHandle [in]

Specifies the handle to the process's image file.    If this information is not available, <i>ImageFileHandle</i> will be <b>NULL</b>.  


### -param Handle [in]

Specifies the handle to the process.  This parameter corresponds to the <b>hProcess</b> field in the CREATE_PROCESS_DEBUG_INFO structure.  If this information is not available, <i>ImageFileHandle</i> will be <b>NULL</b>.  


### -param BaseOffset [in]

Specifies the base address of the process's executable image in the target's memory address space.  If this information is not available, <i>BaseOffset</i> will be <b>NULL</b>.


### -param ModuleSize [in]

Specifies the process's executable image size in bytes.  If this information is not available, <i>ModuleSize</i> will be zero.


### -param ModuleName [in, optional]

Specifies the simplified module name that is used by the debugger engine.  In most cases, this matches the image file name excluding the extension. If this information is not available, <i>ModuleName</i> will be <b>NULL</b>.


### -param ImageName [in, optional]

Specifies the process's executable-image file name, which can include the path.   If this information is not available, <i>ImageName</i> will be <b>NULL</b>.


### -param CheckSum [in]

Specifies the checksum of the process's executable image.  If this information is not available, <i>CheckSum</i> will be zero.


### -param TimeDateStamp [in]

Specifies the time and date stamp of the process's executable-image file.  If this information is not available, <i>TimeDateStamp</i> will be zero.


### -param InitialThreadHandle [in]

Specifies the handle to the process's initial thread.  This parameter corresponds to the <b>hThread</b> field in the CREATE_PROCESS_DEBUG_INFO structure.  If this information is not available, <i>InitialThreadHandle</i> will be <b>NULL</b>. 


### -param ThreadDataOffset [in]

Specifies a block of data that the operating system maintains for this thread.  The actual data in the block is operating system-specific.  If this information is not available, <i>ThreadDataOffset</i> will be <b>NULL</b>. 


### -param StartOffset [in]

Specifies the starting address of the thread in the process's virtual address space.    If this information is not available, <i>StartOffset</i> will be <b>NULL</b>.


## -returns



This method returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541651">DEBUG_STATUS_XXX</a> value, which indicates how the execution of the target should proceed after the engine processes this event.  For details on how the engine treats this value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.




## -remarks



This method is only called by the engine if the DEBUG_EVENT_CREATE_PROCESS flag is set in the mask returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550625">IDebugEventCallbacksWide::GetInterestMask</a>.

For more information about handling events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.  For information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.



