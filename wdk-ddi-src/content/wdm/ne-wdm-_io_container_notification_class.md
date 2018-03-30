---
UID: NE:wdm._IO_CONTAINER_NOTIFICATION_CLASS
title: "_IO_CONTAINER_NOTIFICATION_CLASS"
author: windows-driver-content
description: The IO_CONTAINER_NOTIFICATION_CLASS enumeration contains constants that indicate the classes of events for which a kernel-mode driver can register to receive notifications.
old-location: kernel\io_container_notification_class.htm
old-project: kernel
ms.assetid: cc2ce023-ebb1-4a8e-a06a-e2f11a89d258
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: IO_CONTAINER_NOTIFICATION_CLASS, IO_CONTAINER_NOTIFICATION_CLASS enumeration [Kernel-Mode Driver Architecture], IoMaxContainerNotificationClass, IoSessionStateNotification, _IO_CONTAINER_NOTIFICATION_CLASS, kernel.io_container_notification_class, sysenum_c77c6805-11ce-4368-9c82-085ce99a2a97.xml, wdm/IO_CONTAINER_NOTIFICATION_CLASS, wdm/IoMaxContainerNotificationClass, wdm/IoSessionStateNotification
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows 7 and later versions of the Windows operating system.
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
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	IO_CONTAINER_NOTIFICATION_CLASS
product: Windows
targetos: Windows
req.typenames: IO_CONTAINER_NOTIFICATION_CLASS
req.product: Windows 10 or later.
---

# _IO_CONTAINER_NOTIFICATION_CLASS enumeration


## -description


The <b>IO_CONTAINER_NOTIFICATION_CLASS</b> enumeration contains constants that indicate the classes of events for which a kernel-mode driver can register to receive notifications.


## -enum-fields




### -field IoSessionStateNotification

Session state notifications. The driver uses this enumeration constant to request notifications about changes in the state of user sessions that the driver is interested in.


### -field IoMaxContainerNotificationClass

Specifies the maximum value in this enumeration type. 


## -remarks



To register for notifications, a driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549501">IoRegisterContainerNotification</a> routine and sets this routine's <i>NotificationClass</i> parameter to an <b>IO_CONTAINER_NOTIFICATION_CLASS</b> constant (other than <b>IoMaxContainerNotificationClass</b>). Currently, <b>IoRegisterContainerNotification</b> supports only <i>NotificationClass</i> = <b>IoSessionStateNotification</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549501">IoRegisterContainerNotification</a>
 

 

