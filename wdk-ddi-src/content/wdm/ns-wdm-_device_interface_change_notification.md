---
UID: NS:wdm._DEVICE_INTERFACE_CHANGE_NOTIFICATION
title: _DEVICE_INTERFACE_CHANGE_NOTIFICATION
author: windows-driver-content
description: The DEVICE_INTERFACE_CHANGE_NOTIFICATION structure describes a device interface that has been enabled (arrived) or disabled (removed).
old-location: kernel\device_interface_change_notification.htm
old-project: kernel
ms.assetid: 3b5d67c0-eb3f-4ac1-9f85-f9c673314458
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/DEVICE_INTERFACE_CHANGE_NOTIFICATION, DEVICE_INTERFACE_CHANGE_NOTIFICATION structure [Kernel-Mode Driver Architecture], PDEVICE_INTERFACE_CHANGE_NOTIFICATION, kernel.device_interface_change_notification, PDEVICE_INTERFACE_CHANGE_NOTIFICATION structure pointer [Kernel-Mode Driver Architecture], _DEVICE_INTERFACE_CHANGE_NOTIFICATION, *PDEVICE_INTERFACE_CHANGE_NOTIFICATION, wdm/PDEVICE_INTERFACE_CHANGE_NOTIFICATION, kstruct_a_43e52fa7-54ee-49bd-b822-4daf39ebcdc2.xml, DEVICE_INTERFACE_CHANGE_NOTIFICATION
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
-	DEVICE_INTERFACE_CHANGE_NOTIFICATION
product: Windows
targetos: Windows
req.typenames: *PDEVICE_INTERFACE_CHANGE_NOTIFICATION, DEVICE_INTERFACE_CHANGE_NOTIFICATION
req.product: Windows 10 or later.
---

# _DEVICE_INTERFACE_CHANGE_NOTIFICATION structure


## -description


The <b>DEVICE_INTERFACE_CHANGE_NOTIFICATION</b> structure describes a device interface that has been enabled (arrived) or disabled (removed). The PnP manager sends this structure to a driver that registered a callback routine for notification of <b>EventCategoryDeviceInterfaceChange</b> events.


## -syntax


````
typedef struct _DEVICE_INTERFACE_CHANGE_NOTIFICATION {
  USHORT          Version;
  USHORT          Size;
  GUID            Event;
  GUID            InterfaceClassGuid;
  PUNICODE_STRING SymbolicLinkName;
} DEVICE_INTERFACE_CHANGE_NOTIFICATION, *PDEVICE_INTERFACE_CHANGE_NOTIFICATION;
````


## -struct-fields




### -field Version

Specifies the version of the data structure, currently 1. 


### -field Size

Specifies the size of the structure, in bytes, including the size of the standard first three members plus the event-specific data. 


### -field Event

Specifies a GUID identifying the event:  GUID_DEVICE_INTERFACE_ARRIVAL or GUID_DEVICE_INTERFACE_REMOVAL. The GUIDs are defined in Wdmguid.h. 


### -field InterfaceClassGuid

Specifies the class of the device interface that has just been enabled or disabled.


### -field SymbolicLinkName

Pointer to a Unicode string that contains the name of the symbolic link for the device interface. 


## -remarks


This structure is allocated from paged memory.



## -see-also

<a href="..\wdm\ns-wdm-_plugplay_notification_header.md">PLUGPLAY_NOTIFICATION_HEADER</a>

<a href="..\wdm\nf-wdm-ioregisterplugplaynotification.md">IoRegisterPlugPlayNotification</a>

<a href="..\wdm\ns-wdm-_hwprofile_change_notification.md">HWPROFILE_CHANGE_NOTIFICATION</a>

<a href="..\wdm\ns-wdm-_target_device_removal_notification.md">TARGET_DEVICE_REMOVAL_NOTIFICATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20DEVICE_INTERFACE_CHANGE_NOTIFICATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

