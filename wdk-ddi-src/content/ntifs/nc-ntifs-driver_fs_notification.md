---
UID: NC:ntifs.DRIVER_FS_NOTIFICATION
title: DRIVER_FS_NOTIFICATION
author: windows-driver-content
description: A PDRIVER_FS_NOTIFICATION-typed routine is called by the operating system when a file system registers or unregisters itself by using IoRegisterFileSystem or IoUnregisterFileSystem.
old-location: ifsk\pdriver_fs_notification.htm
old-project: ifsk
ms.assetid: 571aaa9b-8620-46ff-af29-19b00804e0ad
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: DRIVER_FS_NOTIFICATION, DriverNotificationRoutine, DriverNotificationRoutine routine [Installable File System Drivers], FilterCallbacks_5b421108-0db7-47ba-afba-3a8b79a61d66.xml, ifsk.pdriver_fs_notification, ntifs/DriverNotificationRoutine
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows 2000 and later versions of the Windows operating system.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ntifs.h
apiname:
-	PDRIVER_FS_NOTIFICATION
product: Windows
targetos: Windows
req.typenames: VOLUME_READ_PLEX_INPUT, *PVOLUME_READ_PLEX_INPUT
---

# DRIVER_FS_NOTIFICATION callback


## -description


A PDRIVER_FS_NOTIFICATION-typed routine is called by the operating system when a file system registers or unregisters itself by using <a href="..\ntifs\nf-ntifs-ioregisterfilesystem.md">IoRegisterFileSystem</a> or <a href="..\ntifs\nf-ntifs-iounregisterfilesystem.md">IoUnregisterFileSystem</a>.


## -prototype


````
DRIVER_FS_NOTIFICATION DriverNotificationRoutine;

VOID  DriverNotificationRoutine(
  _In_ struct _DEVICE_OBJECT *DeviceObject,
  _In_ BOOLEAN               FsActive
)
{ ... }
````


## -parameters




### -param *DeviceObject [in]

A pointer to a file system device object for which the notification was called.


### -param FsActive [in]

A Boolean value that indicates whether the file system has registered (TRUE) or unregistered (FALSE) itself as an active file system.


## -returns



This routine does not return a value.




## -remarks



You must declare the callback function by using the <i>DRIVER_FS_NOTIFICATION</i> type. For more information, see the following Example section.


#### Examples

To define a <b>DriverFSNotificationRoutine</b> callback routine that is named <b>MyDriverNotification</b>, you must first provide a function declaration that the Static Driver Verify (SDV) and other verification tools require, as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>DRIVER_FS_NOTIFICATION MyDriverFSNotification;</pre>
</td>
</tr>
</table></span></div>
And then implement your callback routine as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
MyDriverFSNotification (
    __in struct _DEVICE_OBJECT *DeviceObject,
    __in BOOLEAN FsActive
)
{ . . . }</pre>
</td>
</tr>
</table></span></div>
Note that the callback type is declared in <i>Ntifs.h</i> as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
DRIVER_FS_NOTIFICATION (
  __in struct _DEVICE_OBJECT *DeviceObject,
  __in BOOLEAN FsActive
  );
typedef DRIVER_FS_NOTIFICATION *PDRIVER_FS_NOTIFICATION;</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\ntifs\nf-ntifs-ioregisterfsregistrationchange.md">IoRegisterFsRegistrationChange</a>



<a href="..\ntifs\nf-ntifs-ioregisterfsregistrationchangeex.md">IoRegisterFsRegistrationChangeEx</a>



<a href="..\ntifs\nf-ntifs-iounregisterfsregistrationchange.md">IoUnregisterFsRegistrationChange</a>



<a href="..\ntifs\nf-ntifs-ioregisterfsregistrationchangemountaware.md">IoRegisterFsRegistrationChangeMountAware</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PDRIVER_FS_NOTIFICATION routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

