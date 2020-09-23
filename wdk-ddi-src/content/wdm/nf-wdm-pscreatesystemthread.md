---
UID: NF:wdm.PsCreateSystemThread
title: PsCreateSystemThread function (wdm.h)
description: The PsCreateSystemThread routine creates a system thread that executes in kernel mode and returns a handle for the thread.
old-location: kernel\pscreatesystemthread.htm
tech.root: kernel
ms.assetid: 4f6bfae4-8515-4fc4-aab3-9e16dbeda6da
ms.date: 04/30/2018
keywords: ["PsCreateSystemThread function"]
ms.keywords: PsCreateSystemThread, PsCreateSystemThread routine [Kernel-Mode Driver Architecture], k108_858fe76b-471d-42c9-8844-c14ae33bd235.xml, kernel.pscreatesystemthread, wdm/PsCreateSystemThread
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlPsPassive, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PsCreateSystemThread
 - wdm/PsCreateSystemThread
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PsCreateSystemThread
---

# PsCreateSystemThread function


## -description

The <b>PsCreateSystemThread</b> routine creates a system thread that executes in kernel mode and returns a handle for the thread.

## -parameters

### -param ThreadHandle 

[out]
Points to a variable that will receive the handle. The driver must close the handle with <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a> once the handle is no longer in use. This handle is a kernel handle for Windows Vista and later versions of Windows. In earlier versions of Windows, the handle might not be a kernel handle.

### -param DesiredAccess 

[in]
Specifies the <a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> value that represents the requested types of access to the created thread.

### -param ObjectAttributes 

[in, optional]
Points to a structure that specifies the object's attributes. OBJ_PERMANENT, OBJ_EXCLUSIVE, and OBJ_OPENIF are not valid attributes for a thread object. On Windows XP and later versions of Windows, if the caller is not running in the system process context, it must set the OBJ_KERNEL_HANDLE attribute for <i>ObjectAttributes</i>. Drivers for Microsoft Windows 2000 and Windows 98/Me must only call <b>PsCreateSystemThread</b> from the system process context. For Windows Vista and later versions of Windows, the handle will be a kernel handle.

### -param ProcessHandle 

[in, optional]
Specifies an open handle for the process in whose address space the thread is to be run. The caller's thread must have PROCESS_CREATE_THREAD access to this process. If this parameter is not supplied, the thread will be created in the initial system process. This value should be <b>NULL</b> for a driver-created thread. Use the <b>NtCurrentProcess</b> macro, defined in Ntddk.h, to specify the current process.

### -param ClientId 

[out, optional]
Points to a structure that receives the client identifier of the new thread. This value should be <b>NULL</b> for a driver-created thread.

### -param StartRoutine 

[in]
The entry point for the newly created system thread. This parameter is a function pointer to a <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-kstart_routine">ThreadStart</a> routine that receives a single argument, which is the <i>StartContext</i> parameter value supplied by the caller.

### -param StartContext 

[in, optional]
Supplies a single argument that is passed to the thread when it begins execution.

## -returns

<b>PsCreateSystemThread</b> returns STATUS_SUCCESS if the thread was created.

## -remarks

Drivers that create device-dedicated threads call this routine, either when they initialize or when I/O requests begin to come in to such a driver's Dispatch routines. For example, a driver might create such a thread when it receives an asynchronous device control request.

<b>PsCreateSystemThread</b> creates a kernel-mode thread that begins a separate thread of execution within the system. Such a system thread has no TEB or user-mode context and runs only in kernel mode.

If the input <i>ProcessHandle</i> is <b>NULL</b>, the created thread is associated with the system process. Such a thread continues running until either the system is shut down or the thread terminates itself by calling <b>PsTerminateSystemThread</b>.

Starting with Windows XP, driver routines that run in a process context other than that of the system process must set the OBJ_KERNEL_HANDLE attribute for the <i>ObjectAttributes</i> parameter of <b>PsCreateSystemThread</b>. This restricts the use of the handle returned by <b>PsCreateSystemThread</b> to processes running in kernel mode. Otherwise, the thread handle can be accessed by the process in whose context the driver is running. Drivers can set the OBJ_KERNEL_HANDLE attribute as follows.


```
InitializeObjectAttributes(&ObjectAttributes, NULL, OBJ_KERNEL_HANDLE, NULL, NULL);
```

Drivers for Windows 2000 and Windows 98/Me must call <b>PsCreateSystemThread</b> only from the system process context.

For more information about the <i>StartContext</i> parameter, see <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-kstart_routine">ThreadStart</a>.

 The newly created system thread runs at PASSIVE_LEVEL inside a critical region with <a href="/windows-hardware/drivers/kernel/types-of-apcs">normal kernel APCs</a> disabled.

## -see-also

<a href="/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kesetbaseprioritythread">KeSetBasePriorityThread</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kesetprioritythread">KeSetPriorityThread</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-psterminatesystemthread">PsTerminateSystemThread</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-kstart_routine">ThreadStart</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-zwsetinformationthread">ZwSetInformationThread</a>