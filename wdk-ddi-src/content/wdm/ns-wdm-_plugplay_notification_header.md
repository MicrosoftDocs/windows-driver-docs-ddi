---
UID: NS:wdm._PLUGPLAY_NOTIFICATION_HEADER
title: "_PLUGPLAY_NOTIFICATION_HEADER"
author: windows-driver-content
description: A PLUGPLAY_NOTIFICATION_HEADER structure is included at the beginning of each PnP notification structure, such as a DEVICE_INTERFACE_CHANGE_NOTIFICATION structure.
old-location: kernel\plugplay_notification_header.htm
old-project: kernel
ms.assetid: b2245810-8f3c-4955-b341-46df4a71707c
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PPLUGPLAY_NOTIFICATION_HEADER, PLUGPLAY_NOTIFICATION_HEADER, PLUGPLAY_NOTIFICATION_HEADER structure [Kernel-Mode Driver Architecture], PPLUGPLAY_NOTIFICATION_HEADER, PPLUGPLAY_NOTIFICATION_HEADER structure pointer [Kernel-Mode Driver Architecture], _PLUGPLAY_NOTIFICATION_HEADER, kernel.plugplay_notification_header, kstruct_c_3b18984d-35cf-4787-b887-a8916a89569b.xml, wdm/PLUGPLAY_NOTIFICATION_HEADER, wdm/PPLUGPLAY_NOTIFICATION_HEADER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	PLUGPLAY_NOTIFICATION_HEADER
product: Windows
targetos: Windows
req.typenames: PLUGPLAY_NOTIFICATION_HEADER, *PPLUGPLAY_NOTIFICATION_HEADER
req.product: Windows 10 or later.
---

# _PLUGPLAY_NOTIFICATION_HEADER structure


## -description


A <b>PLUGPLAY_NOTIFICATION_HEADER</b> structure is included at the beginning of each PnP notification structure, such as a <a href="..\wdm\ns-wdm-_device_interface_change_notification.md">DEVICE_INTERFACE_CHANGE_NOTIFICATION</a> structure.


## -syntax


````
typedef struct _PLUGPLAY_NOTIFICATION_HEADER {
  USHORT Version;
  USHORT Size;
  GUID   Event;
} PLUGPLAY_NOTIFICATION_HEADER, *PPLUGPLAY_NOTIFICATION_HEADER;
````


## -struct-fields




### -field Version

Specifies the version of the data structure, currently set to 1. 


### -field Size

Specifies the size of the structure, in bytes. 


### -field Event

Specifies a GUID identifying the event. 


## -remarks



Drivers can cast a PnP notification structure to this type to access the <b>Event</b> field and identify the exact type of the structure.




## -see-also

<a href="..\wdm\ns-wdm-_device_interface_change_notification.md">DEVICE_INTERFACE_CHANGE_NOTIFICATION</a>



<a href="..\wdm\ns-wdm-_target_device_removal_notification.md">TARGET_DEVICE_REMOVAL_NOTIFICATION</a>



<a href="..\wdm\nf-wdm-ioregisterplugplaynotification.md">IoRegisterPlugPlayNotification</a>



<a href="..\wdm\ns-wdm-_target_device_custom_notification.md">TARGET_DEVICE_CUSTOM_NOTIFICATION</a>



<a href="..\wdm\ns-wdm-_hwprofile_change_notification.md">HWPROFILE_CHANGE_NOTIFICATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PLUGPLAY_NOTIFICATION_HEADER structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

