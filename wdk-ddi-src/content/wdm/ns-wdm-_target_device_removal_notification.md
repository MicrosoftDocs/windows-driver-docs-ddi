---
UID: NS:wdm._TARGET_DEVICE_REMOVAL_NOTIFICATION
title: _TARGET_DEVICE_REMOVAL_NOTIFICATION (wdm.h)
description: The TARGET_DEVICE_REMOVAL_NOTIFICATION structure describes a device-removal event. The PnP manager sends this structure to a driver that registered a callback routine for notification of EventCategoryTargetDeviceChange events.
old-location: kernel\target_device_removal_notification.htm
tech.root: kernel
ms.assetid: a14656ca-131a-4722-aae7-041eddc8517a
ms.date: 04/30/2018
ms.keywords: "*PTARGET_DEVICE_REMOVAL_NOTIFICATION, PTARGET_DEVICE_REMOVAL_NOTIFICATION, PTARGET_DEVICE_REMOVAL_NOTIFICATION structure pointer [Kernel-Mode Driver Architecture], TARGET_DEVICE_REMOVAL_NOTIFICATION, TARGET_DEVICE_REMOVAL_NOTIFICATION structure [Kernel-Mode Driver Architecture], _TARGET_DEVICE_REMOVAL_NOTIFICATION, kernel.target_device_removal_notification, kstruct_d_9b46ee83-c40a-435c-a544-456672ebca33.xml, wdm/PTARGET_DEVICE_REMOVAL_NOTIFICATION, wdm/TARGET_DEVICE_REMOVAL_NOTIFICATION"
ms.topic: struct
f1_keywords:
 - "wdm/TARGET_DEVICE_REMOVAL_NOTIFICATION"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdm.h
api_name:
- TARGET_DEVICE_REMOVAL_NOTIFICATION
product:
- Windows
targetos: Windows
req.typenames: TARGET_DEVICE_REMOVAL_NOTIFICATION, *PTARGET_DEVICE_REMOVAL_NOTIFICATION
---

# _TARGET_DEVICE_REMOVAL_NOTIFICATION structure


## -description


The <b>TARGET_DEVICE_REMOVAL_NOTIFICATION</b> structure describes a device-removal event. The PnP manager sends this structure to a driver that registered a callback routine for notification of <b>EventCategoryTargetDeviceChange</b> events.


## -struct-fields




### -field Version

Specifies the version of the data structure, currently set to 1. 


### -field Size

Specifies the size of the structure, in bytes, including the size of the standard first three members plus the event-specific data. 


### -field Event

Specifies a GUID identifying the event: GUID_TARGET_DEVICE_QUERY_REMOVE, GUID_TARGET_DEVICE_REMOVE_COMPLETE, or GUID_TARGET_DEVICE_REMOVE_CANCELLED. These GUIDs are defined in Wdmguid.h.


### -field FileObject

Pointer to a file object for the device. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_interface_change_notification">DEVICE_INTERFACE_CHANGE_NOTIFICATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_hwprofile_change_notification">HWPROFILE_CHANGE_NOTIFICATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ioregisterplugplaynotification">IoRegisterPlugPlayNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_target_device_custom_notification">TARGET_DEVICE_CUSTOM_NOTIFICATION</a>
 

 

