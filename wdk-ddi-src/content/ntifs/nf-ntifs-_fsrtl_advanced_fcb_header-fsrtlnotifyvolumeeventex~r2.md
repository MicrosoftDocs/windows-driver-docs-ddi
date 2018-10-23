---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlNotifyVolumeEventEx~r2
title: FsRtlNotifyVolumeEventEx function
author: windows-driver-content
description: The FsRtlNotifyVolumeEventEx routine notifies any registered applications that a volume event is occurring. Volume events include the volume being locked, unlocked, mounted, or made read-only.
old-location: ifsk\fsrtlnotifyvolumeeventex.htm
tech.root: ifsk
ms.assetid: 0792e139-0217-4882-b2df-e69452118fc9
ms.date: 03/29/2018
ms.keywords: FsRtlNotifyVolumeEventEx, FsRtlNotifyVolumeEventEx routine [Installable File System Drivers], fsrtlref_421ebbf6-0678-4b66-a7c3-00f5914ea05c.xml, ifsk.fsrtlnotifyvolumeeventex, ntifs/FsRtlNotifyVolumeEventEx
ms.topic: function
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later version of the Windows operating system.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlNotifyVolumeEventEx
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlNotifyVolumeEventEx function


## -description


The <b>FsRtlNotifyVolumeEventEx</b> routine notifies any registered applications that a volume event is occurring. Volume events include the volume  being locked, unlocked, mounted, or made read-only.


## -parameters




### -param FileObject [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff545834">FILE_OBJECT</a> that specifies a volume.


### -param EventCode [in]

An event code for the event that is occurring. For a table of event codes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547060">FsRtlNotifyVolumeEvent</a>.


### -param Event [in]

A pointer to the initialized custom notification structure (<a href="https://msdn.microsoft.com/library/windows/hardware/ff564596">TARGET_DEVICE_CUSTOM_NOTIFICATION</a>) to use.


## -returns



Returns STATUS_SUCCESS on success or another relevant NTSTATUS value, such as STATUS_INVALID_PARAMETER, if the <i>EventCode</i> is not valid.




## -remarks



<div class="alert"><b>Note</b>   When you specify the <i>Event</i> parameter as a custom volume notification, set the following members of the TARGET_DEVICE_CUSTOM_NOTIFICATION object as follows:<p class="note">Version to 1.

<p class="note"><i>FileObject</i> to <b>NULL</b>.

</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547060">FsRtlNotifyVolumeEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549526">IoRegisterPlugPlayNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550398">IoUnregisterPlugPlayNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564596">TARGET_DEVICE_CUSTOM_NOTIFICATION</a>
 

 

