---
UID: NS:wdm._HWPROFILE_CHANGE_NOTIFICATION
title: "_HWPROFILE_CHANGE_NOTIFICATION"
author: windows-driver-content
description: The HWPROFILE_CHANGE_NOTIFICATION structure describes an event related to a hardware profile configuration change.
old-location: kernel\hwprofile_change_notification.htm
old-project: kernel
ms.assetid: 3b6fe106-2440-4bc6-a3ae-9bb8b18f8094
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PHWPROFILE_CHANGE_NOTIFICATION structure pointer [Kernel-Mode Driver Architecture], kernel.hwprofile_change_notification, PHWPROFILE_CHANGE_NOTIFICATION, *PHWPROFILE_CHANGE_NOTIFICATION, wdm/PHWPROFILE_CHANGE_NOTIFICATION, wdm/HWPROFILE_CHANGE_NOTIFICATION, HWPROFILE_CHANGE_NOTIFICATION structure [Kernel-Mode Driver Architecture], kstruct_b_2e8d0c69-abe9-49a9-96f6-fba3b0020ff8.xml, _HWPROFILE_CHANGE_NOTIFICATION, HWPROFILE_CHANGE_NOTIFICATION
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
-	Wdm.h
apiname:
-	HWPROFILE_CHANGE_NOTIFICATION
product: Windows
targetos: Windows
req.typenames: HWPROFILE_CHANGE_NOTIFICATION, *PHWPROFILE_CHANGE_NOTIFICATION
req.product: Windows 10 or later.
---

# _HWPROFILE_CHANGE_NOTIFICATION structure


## -description


The <b>HWPROFILE_CHANGE_NOTIFICATION</b> structure describes an event related to a hardware profile configuration change. The PnP manager sends this structure to a driver that registered a callback routine for notification of <b>EventCategoryHardwareProfileChange</b> events.


## -syntax


````
typedef struct _HWPROFILE_CHANGE_NOTIFICATION {
  USHORT Version;
  USHORT Size;
  GUID   Event;
} HWPROFILE_CHANGE_NOTIFICATION, *PHWPROFILE_CHANGE_NOTIFICATION;
````


## -struct-fields




### -field Version

Specifies the version of the data structure, currently 1. 


### -field Size

Specifies the size of the structure, in bytes including the size of the standard first three members plus the event-specific data. 


### -field Event

Specifies a GUID identifying the event: GUID_HWPROFILE_QUERY_CHANGE, GUID_HWPROFILE_CHANGE_COMPLETE, or GUID_HWPROFILE_CHANGE_CANCELLED. The GUIDs are defined in Wdmguid.h.


## -remarks



There is no event-specific data for a hardware-profile-change event. 




## -see-also

<a href="..\wdm\ns-wdm-_target_device_removal_notification.md">TARGET_DEVICE_REMOVAL_NOTIFICATION</a>



<a href="..\wdm\ns-wdm-_device_interface_change_notification.md">DEVICE_INTERFACE_CHANGE_NOTIFICATION</a>



<a href="..\wdm\nf-wdm-ioregisterplugplaynotification.md">IoRegisterPlugPlayNotification</a>



<a href="..\wdm\ns-wdm-_plugplay_notification_header.md">PLUGPLAY_NOTIFICATION_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20HWPROFILE_CHANGE_NOTIFICATION structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

