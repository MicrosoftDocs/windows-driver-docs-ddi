---
UID: NS:wdm._TARGET_DEVICE_REMOVAL_NOTIFICATION
title: _TARGET_DEVICE_REMOVAL_NOTIFICATION
author: windows-driver-content
description: The TARGET_DEVICE_REMOVAL_NOTIFICATION structure describes a device-removal event. The PnP manager sends this structure to a driver that registered a callback routine for notification of EventCategoryTargetDeviceChange events.
old-location: kernel\target_device_removal_notification.htm
old-project: kernel
ms.assetid: a14656ca-131a-4722-aae7-041eddc8517a
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _TARGET_DEVICE_REMOVAL_NOTIFICATION, *PTARGET_DEVICE_REMOVAL_NOTIFICATION, TARGET_DEVICE_REMOVAL_NOTIFICATION
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
req.alt-api: TARGET_DEVICE_REMOVAL_NOTIFICATION
req.alt-loc: wdm.h
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
req.typenames: *PTARGET_DEVICE_REMOVAL_NOTIFICATION, TARGET_DEVICE_REMOVAL_NOTIFICATION
req.product: Windows 10 or later.
---

# _TARGET_DEVICE_REMOVAL_NOTIFICATION structure



## -description
The <b>TARGET_DEVICE_REMOVAL_NOTIFICATION</b> structure describes a device-removal event. The PnP manager sends this structure to a driver that registered a callback routine for notification of <b>EventCategoryTargetDeviceChange</b> events.



## -syntax

````
typedef struct _TARGET_DEVICE_REMOVAL_NOTIFICATION {
  USHORT       Version;
  USHORT       Size;
  GUID         Event;
  PFILE_OBJECT FileObject;
} TARGET_DEVICE_REMOVAL_NOTIFICATION, *PTARGET_DEVICE_REMOVAL_NOTIFICATION;
````


## -struct-fields

### -field Version

Specifies the version of the data structure, currently set to 1. 


### -field Size

Specifies the size of the structure, in bytes, including the size of the standard first three members plus the event-specific data. 


### -field Event

Specifies a GUID identifying the event: GUID_TARGET_DEVICE_QUERY_REMOVE, GUID_TARGET_DEVICE_REMOVE_COMPLETE, or GUID_TARGET_DEVICE_REMOVE_CANCELLED. These GUIDs are defined in Wdmguid.h.


### -field FileObject

Pointer to a file object for the device. 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm-_device_interface_change_notification.md">DEVICE_INTERFACE_CHANGE_NOTIFICATION</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_hwprofile_change_notification.md">HWPROFILE_CHANGE_NOTIFICATION</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-ioregisterplugplaynotification.md">IoRegisterPlugPlayNotification</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_target_device_custom_notification.md">TARGET_DEVICE_CUSTOM_NOTIFICATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20TARGET_DEVICE_REMOVAL_NOTIFICATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

