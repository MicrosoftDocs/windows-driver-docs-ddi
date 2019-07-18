---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlNotifyVolumeEvent
title: FsRtlNotifyVolumeEvent function (ntifs.h)
description: The FsRtlNotifyVolumeEvent routine notifies any registered applications that a volume event is occurring.
old-location: ifsk\fsrtlnotifyvolumeevent.htm
tech.root: ifsk
ms.assetid: a630d986-10a7-4b3f-a5b4-05de7879b146
ms.date: 04/16/2018
ms.keywords: FsRtlNotifyVolumeEvent, FsRtlNotifyVolumeEvent routine [Installable File System Drivers], fsrtlref_a242139a-dc66-4522-85a2-4f910d999d4d.xml, ifsk.fsrtlnotifyvolumeevent, ntifs/FsRtlNotifyVolumeEvent
ms.topic: function
f1_keywords:
 - "ntifs/FsRtlNotifyVolumeEvent"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows XP and later.
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
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlNotifyVolumeEvent
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# FsRtlNotifyVolumeEvent function


## -description


The <b>FsRtlNotifyVolumeEvent</b> routine notifies any registered applications that a volume event is occurring. 


## -parameters




### -param FileObject [in]

A pointer to a file object for the given volume. 


### -param EventCode [in]

Specifies an event code for the event that is occurring. This code can be one of the following values.

<table>
<tr>
<th>Event Code</th>
<th>PnP event GUID</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FSRTL_VOLUME_BACKGROUND_FORMAT

</td>
<td>
GUID_IO_VOLUME_BACKGROUND_FORMAT

</td>
<td>
A background format operation has been initiated.

</td>
</tr>
<tr>
<td>
FSRTL_VOLUME_CHANGE_SIZE

</td>
<td>
GUID_IO_VOLUME_CHANGE_SIZE

</td>
<td>
The size of the file system on the volume has changed. For Windows Server 2003 and Windows XP/2000, this value is not supported.

</td>
</tr>
<tr>
<td>
FSRTL_VOLUME_DISMOUNT

</td>
<td>
GUID_IO_VOLUME_DISMOUNT

</td>
<td>
The volume is being dismounted.

</td>
</tr>
<tr>
<td>
FSRTL_VOLUME_DISMOUNT_FAILED

</td>
<td>
GUID_IO_VOLUME_DISMOUNT_FAILED

</td>
<td>
The volume dismount failed.

</td>
</tr>
<tr>
<td>
FSRTL_VOLUME_FORCED_CLOSED

</td>
<td>
GUID_IO_VOLUME_FORCE_CLOSED

</td>
<td>
The volume has been made read-only by the file system. This flag is available on Windows Vista and later.

</td>
</tr>
<tr>
<td>
FSRTL_VOLUME_INFO_MAKE_COMPAT

</td>
<td>
GUID_IO_VOLUME_INFO_MAKE_COMPAT

</td>
<td>
The volume media has been removed, but it is in an incompatible state and might not be readable by a different removable-media storage device. This flag is available on Windows Vista and later.

</td>
</tr>
<tr>
<td>
FSRTL_VOLUME_LOCK

</td>
<td>
GUID_IO_VOLUME_LOCK

</td>
<td>
The volume is being locked.

</td>
</tr>
<tr>
<td>
FSRTL_VOLUME_LOCK_FAILED

</td>
<td>
GUID_IO_VOLUME_LOCK_FAILED

</td>
<td>
The volume lock failed.

</td>
</tr>
<tr>
<td>
FSRTL_VOLUME_MOUNT

</td>
<td>
GUID_IO_VOLUME_MOUNT

</td>
<td>
The volume is being mounted.

</td>
</tr>
<tr>
<td>
FSRTL_VOLUME_NEEDS_CHKDSK

</td>
<td>
GUID_IO_VOLUME_NEED_CHKDSK

</td>
<td>
Data corruption was detected on the volume and it needs to be corrected by running Chkdsk. This flag is available on Windows Vista and later.

</td>
</tr>
<tr>
<td>
FSRTL_VOLUME_PREPARING_EJECT

</td>
<td>
GUID_IO_VOLUME_PREPARING_EJECT

</td>
<td>
The file system is preparing the disc to be ejected. For Windows Server 2003 and Windows XP/2000, this value is not supported.

</td>
</tr>
<tr>
<td>
FSRTL_VOLUME_UNLOCK

</td>
<td>
GUID_IO_VOLUME_UNLOCK

</td>
<td>
The volume is being unlocked.

</td>
</tr>
<tr>
<td>
FSRTL_VOLUME_WEARING_OUT

</td>
<td>
GUID_IO_VOLUME_WEARING_OUT

</td>
<td>
The volume media is wearing out. This flag is available on Windows Vista and later.

</td>
</tr>
<tr>
<td>
FSRTL_VOLUME_WORM_NEAR_FULL

</td>
<td>
GUID_IO_VOLUME_WORM_NEAR_FULL

</td>
<td>
The volume is a write-once, read-many (WORM) volume and it is nearly full. This flag is available on Windows Vista and later.

</td>
</tr>
</table>
 


## -returns



<b>FsRtlNotifyVolumeEvent</b> returns the status of the notification. 




## -remarks



File systems call <b>FsRtlNotifyVolumeEvent</b> to notify any registered user-mode applications that a volume event is occurring. 

PnP event GUID values are defined in Ioevent.h. 

To register for volume event notification, applications must call the Microsoft Win32 <b>RegisterDeviceNotification</b> function. For more information, see the Device Management section in the Microsoft Windows SDK documentation. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ioregisterplugplaynotification">IoRegisterPlugPlayNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iounregisterplugplaynotification">IoUnregisterPlugPlayNotification</a>
 

 

