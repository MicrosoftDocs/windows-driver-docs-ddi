---
UID: NC:ntddk.PLOAD_IMAGE_NOTIFY_ROUTINE
title: PLOAD_IMAGE_NOTIFY_ROUTINE (ntddk.h)
description: Called by the operating system to notify the driver when a driver image or a user image (for example, a DLL or EXE) is mapped into virtual memory.
old-location: kernel\pload_image_notify_routine.htm
tech.root: kernel
ms.assetid: 613962D6-DF27-4AAE-BD8F-6BC0A538D7F8
ms.date: 04/30/2018
keywords: ["PLOAD_IMAGE_NOTIFY_ROUTINE callback function"]
ms.keywords: PLOAD_IMAGE_NOTIFY_ROUTINE, PLOAD_IMAGE_NOTIFY_ROUTINE callback, SetLoadImageNotifyRoutine, SetLoadImageNotifyRoutine callback function [Kernel-Mode Driver Architecture], kernel.pload_image_notify_routine, ntddk/SetLoadImageNotifyRoutine
f1_keywords:
 - "ntddk/SetLoadImageNotifyRoutine"
 - "SetLoadImageNotifyRoutine"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ntddk.h
api_name:
- SetLoadImageNotifyRoutine
targetos: Windows
req.typenames: 
---

# PLOAD_IMAGE_NOTIFY_ROUTINE callback function


## -description


Called by the operating system to notify the driver when a driver image or a user image (for example, a DLL or EXE) is mapped into virtual memory. The operating system invokes this routine after an image has been mapped to memory, but before its entrypoint is called.
<div class="alert"><b>Warning</b>  The actions that  you can perform in this routine are restricted for safe calls. See <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/windows-kernel-mode-process-and-thread-manager#best">Best Practices</a>. </div><div> </div>

## -parameters




### -param FullImageName [in, optional]

A pointer to a buffered Unicode string that identifies the executable image file. (The <i>FullImageName</i> parameter can be <b>NULL</b> in cases in which the operating system is unable to obtain the full name of the image at process creation time.) 


### -param ProcessId [in]

The process ID of the process in which the image has been mapped, but this handle is zero if the newly loaded image is a driver.


### -param ImageInfo [in]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_image_info">IMAGE_INFO</a> structure that contains image information. See Remarks.


## -remarks



Highest-level system-profiling drivers can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetloadimagenotifyroutine">PsSetLoadImageNotifyRoutine</a> to set up their load-image notify routine.

The operating system does not call load-image notify routines when sections created with the SEC_IMAGE_NO_EXECUTE attribute are mapped to virtual memory.

In Windows 7, Windows Server 2008 R2, and earlier versions of Windows, the operating system holds an internal system lock during calls to load-image notify routines for images loaded in user process address space (user space). To avoid deadlocks, load-image notify routines must not call system routines that map, allocate, query, free, or perform other operations on user-space virtual memory.

A driver must remove any callbacks it registers before it unloads. You can remove the callback by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psremoveloadimagenotifyroutine">PsRemoveLoadImageNotifyRoutine</a> routine.

When the main executable image for a newly created process is loaded, the load-image notify routine runs in the context of the new process. The operating system calls the driver's load-image notify routine at PASSIVE_LEVEL inside a critical region with <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/types-of-apcs">normal kernel APCs</a> always disabled and sometimes with both kernel and special APCs disabled.


When the load-image notify routine is called, the input <i>FullImageName</i> points to a buffered Unicode string that identifies the executable image file. (The <i>FullImageName</i> parameter can be <b>NULL</b> in cases in which the operating system is unable to obtain the full name of the image at process creation time.) The <i>ProcessId</i> handle identifies the process in which the image has been mapped, but this handle is zero if the newly loaded image is a driver. To see the format of the buffered data at <i>ImageInfo</i>, see  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_image_info">IMAGE_INFO</a>. If the <b>ExtendedInfoPresent</b> flag is set in the <b>IMAGE_INFO</b> structure, the information is part of a larger, extended version of the image information structure, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_image_info_ex">IMAGE_INFO_EX</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_image_info">IMAGE_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_image_info_ex">IMAGE_INFO_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetloadimagenotifyroutine">PsSetLoadImageNotifyRoutine</a>
 

 

