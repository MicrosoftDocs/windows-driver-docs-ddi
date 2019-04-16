---
UID: NE:wdm._IO_NOTIFICATION_EVENT_CATEGORY
title: IO_NOTIFICATION_EVENT_CATEGORY
author: windows-driver-content
description: 
tech.root:
ms.assetid: 9dbe9f82-a042-4d9e-b8e5-98725fb55e06
ms.author: windowsdriverdev
ms.date: 
ms.topic: enum
ms.keywords: IO_NOTIFICATION_EVENT_CATEGORY, IO_NOTIFICATION_EVENT_CATEGORY, 
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: IO_NOTIFICATION_EVENT_CATEGORY
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - wdm.h
api_name: 
 - IO_NOTIFICATION_EVENT_CATEGORY
product: 
 - Windows
targetos: Windows
ms.custom: 19H1
---

# IO_NOTIFICATION_EVENT_CATEGORY enumeration

## -description

Specifies the category of PnP event for which the callback routine is being registered.  Used in [**IoRegisterPlugPlayNotification**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ioregisterplugplaynotification).

## -enum-fields

### -field EventCategoryReserved 

Reserved for system use.

### -field EventCategoryHardwareProfileChange

PnP events in this category include query-change (GUID_HWPROFILE_QUERY_CHANGE), change-complete (GUID_HWPROFILE_CHANGE_COMPLETE), and change-cancel (GUID_HWPROFILE_CHANGE_CANCELLED) of a hardware profile.

### -field EventCategoryDeviceInterfaceChange

PnP events in this category include the arrival (enabling) of a new instance of a [device interface class](https://docs.microsoft.com/windows-hardware/drivers/install/overview-of-device-interface-classes) (GUID_DEVICE_INTERFACE_ARRIVAL), or the removal (disabling) of an existing device interface instance (GUID_DEVICE_INTERFACE_REMOVAL).

### -field EventCategoryTargetDeviceChange

PnP events in this category include events related to removing a device: the device's drivers received a query-remove IRP (GUID_TARGET_DEVICE_QUERY_REMOVE), the drivers completed a remove IRP (GUID_TARGET_DEVICE_REMOVE_COMPLETE), or the drivers received a cancel-remove IRP (GUID_TARGET_DEVICE_REMOVE_CANCELLED). This category is also used for custom notification events.

### -field EventCategoryKernelSoftRestart 

Reserved for system use.

## -remarks

## -see-also

[**IoRegisterPlugPlayNotification**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ioregisterplugplaynotification)
