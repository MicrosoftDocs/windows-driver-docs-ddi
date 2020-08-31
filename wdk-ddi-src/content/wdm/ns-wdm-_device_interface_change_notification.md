---
UID: NS:wdm._DEVICE_INTERFACE_CHANGE_NOTIFICATION
title: _DEVICE_INTERFACE_CHANGE_NOTIFICATION (wdm.h)
description: The DEVICE_INTERFACE_CHANGE_NOTIFICATION structure describes a device interface that has been enabled (arrived) or disabled (removed).
old-location: kernel\device_interface_change_notification.htm
tech.root: kernel
ms.assetid: 3b5d67c0-eb3f-4ac1-9f85-f9c673314458
ms.date: 04/30/2018
keywords: ["DEVICE_INTERFACE_CHANGE_NOTIFICATION structure"]
ms.keywords: "*PDEVICE_INTERFACE_CHANGE_NOTIFICATION, DEVICE_INTERFACE_CHANGE_NOTIFICATION, DEVICE_INTERFACE_CHANGE_NOTIFICATION structure [Kernel-Mode Driver Architecture], PDEVICE_INTERFACE_CHANGE_NOTIFICATION, PDEVICE_INTERFACE_CHANGE_NOTIFICATION structure pointer [Kernel-Mode Driver Architecture], _DEVICE_INTERFACE_CHANGE_NOTIFICATION, kernel.device_interface_change_notification, kstruct_a_43e52fa7-54ee-49bd-b822-4daf39ebcdc2.xml, wdm/DEVICE_INTERFACE_CHANGE_NOTIFICATION, wdm/PDEVICE_INTERFACE_CHANGE_NOTIFICATION"
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
targetos: Windows
req.typenames: DEVICE_INTERFACE_CHANGE_NOTIFICATION, *PDEVICE_INTERFACE_CHANGE_NOTIFICATION
f1_keywords:
 - _DEVICE_INTERFACE_CHANGE_NOTIFICATION
 - wdm/_DEVICE_INTERFACE_CHANGE_NOTIFICATION
 - PDEVICE_INTERFACE_CHANGE_NOTIFICATION
 - wdm/PDEVICE_INTERFACE_CHANGE_NOTIFICATION
 - DEVICE_INTERFACE_CHANGE_NOTIFICATION
 - wdm/DEVICE_INTERFACE_CHANGE_NOTIFICATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - DEVICE_INTERFACE_CHANGE_NOTIFICATION
---

# _DEVICE_INTERFACE_CHANGE_NOTIFICATION structure


## -description

The <b>DEVICE_INTERFACE_CHANGE_NOTIFICATION</b> structure describes a device interface that has been enabled (arrived) or disabled (removed). The PnP manager sends this structure to a driver that registered a callback routine for notification of <b>EventCategoryDeviceInterfaceChange</b> events.

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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_hwprofile_change_notification">HWPROFILE_CHANGE_NOTIFICATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioregisterplugplaynotification">IoRegisterPlugPlayNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_plugplay_notification_header">PLUGPLAY_NOTIFICATION_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_target_device_removal_notification">TARGET_DEVICE_REMOVAL_NOTIFICATION</a>

