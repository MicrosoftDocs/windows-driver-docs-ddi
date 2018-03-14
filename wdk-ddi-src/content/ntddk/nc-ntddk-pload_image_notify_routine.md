---
UID: NC:ntddk.PLOAD_IMAGE_NOTIFY_ROUTINE
title: PLOAD_IMAGE_NOTIFY_ROUTINE
author: windows-driver-content
description: Called by the operating system to notify the driver when a driver image or a user image (for example, a DLL or EXE) is mapped into virtual memory.
old-location: kernel\pload_image_notify_routine.htm
old-project: kernel
ms.assetid: 613962D6-DF27-4AAE-BD8F-6BC0A538D7F8
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: PLOAD_IMAGE_NOTIFY_ROUTINE, SetLoadImageNotifyRoutine, SetLoadImageNotifyRoutine callback function [Kernel-Mode Driver Architecture], kernel.pload_image_notify_routine, ntddk/SetLoadImageNotifyRoutine
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ntddk.h
api_name:
-	SetLoadImageNotifyRoutine
product: Windows
targetos: Windows
req.typenames: FILTER_INITIALIZATION_DATA, *PFILTER_INITIALIZATION_DATA
---

# PLOAD_IMAGE_NOTIFY_ROUTINE callback


## -description


Called by the operating system to notify the driver when a driver image or a user image (for example, a DLL or EXE) is mapped into virtual memory. 
<div class="alert"><b>Warning</b>  The actions that  you can perform in this routine are restricted for safe calls. See <a href="https://msdn.microsoft.com/c01b3fd9-7f4e-4d1a-a726-b31b0eebf094">Best Practices</a>. </div><div> </div>

## -prototype


````
PLOAD_IMAGE_NOTIFY_ROUTINE SetLoadImageNotifyRoutine;

void SetLoadImageNotifyRoutine(
  _In_opt_ PUNICODE_STRING FullImageName,
  _In_     HANDLE          ProcessId,
  _In_     PIMAGE_INFO     ImageInfo
)
{ ... }
````


## -parameters




### -param FullImageName [in, optional]

A pointer to a buffered Unicode string that identifies the executable image file. (The <i>FullImageName</i> parameter can be <b>NULL</b> in cases in which the operating system is unable to obtain the full name of the image at process creation time.) 


### -param ProcessId [in]

The process ID of the process in which the image has been mapped, but this handle is zero if the newly loaded image is a driver.


### -param ImageInfo [in]

A pointer to an <a href="..\ntddk\ns-ntddk-_image_info.md">IMAGE_INFO</a> structure that contains image information. See Remarks.


## -returns



This callback function does not return a value.




## -remarks



Highest-level system-profiling drivers can call <a href="..\ntddk\nf-ntddk-pssetloadimagenotifyroutine.md">PsSetLoadImageNotifyRoutine</a> to set up their load-image notify routine.

The operating system does not call load-image notify routines when sections created with the SEC_IMAGE_NO_EXECUTE attribute are mapped to virtual memory.

In Windows 7, Windows Server 2008 R2, and earlier versions of Windows, the operating system holds an internal system lock during calls to load-image notify routines for images loaded in user process address space (user space). To avoid deadlocks, load-image notify routines must not call system routines that map, allocate, query, free, or perform other operations on user-space virtual memory.

A driver must remove any callbacks it registers before it unloads. You can remove the callback by calling the <a href="..\ntddk\nf-ntddk-psremoveloadimagenotifyroutine.md">PsRemoveLoadImageNotifyRoutine</a> routine.

When the main executable image for a newly created process is loaded, the load-image notify routine runs in the context of the new process. The operating system calls the driver's load-image notify routine at PASSIVE_LEVEL inside a critical region with <a href="https://msdn.microsoft.com/74ed953c-1b2a-40b9-9df3-16869b198b38">normal kernel APCs</a> always disabled and sometimes with both kernel and special APCs disabled.


        When the load-image notify routine is called, the input <i>FullImageName</i> points to a buffered Unicode string that identifies the executable image file. (The <i>FullImageName</i> parameter can be <b>NULL</b> in cases in which the operating system is unable to obtain the full name of the image at process creation time.) The <i>ProcessId</i> handle identifies the process in which the image has been mapped, but this handle is zero if the newly loaded image is a driver. To see the format of the buffered data at <i>ImageInfo</i>, see  <a href="..\ntddk\ns-ntddk-_image_info.md">IMAGE_INFO</a>. If the <b>ExtendedInfoPresent</b> flag is set in the <b>IMAGE_INFO</b> structure, the information is part of a larger, extended version of the image information structure, <a href="..\ntddk\ns-ntddk-_image_info_ex.md">IMAGE_INFO_EX</a>.




## -see-also

<a href="..\ntddk\ns-ntddk-_image_info.md">IMAGE_INFO</a>



<a href="..\ntddk\nf-ntddk-pssetloadimagenotifyroutine.md">PsSetLoadImageNotifyRoutine</a>



<a href="..\ntddk\ns-ntddk-_image_info_ex.md">IMAGE_INFO_EX</a>



 

 


