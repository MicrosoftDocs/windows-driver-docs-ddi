---
UID: NS:wdm._HWPROFILE_CHANGE_NOTIFICATION
title: _HWPROFILE_CHANGE_NOTIFICATION (wdm.h)
description: The HWPROFILE_CHANGE_NOTIFICATION structure describes an event related to a hardware profile configuration change.
old-location: kernel\hwprofile_change_notification.htm
tech.root: kernel
ms.assetid: 3b6fe106-2440-4bc6-a3ae-9bb8b18f8094
ms.date: 04/30/2018
keywords: ["_HWPROFILE_CHANGE_NOTIFICATION structure"]
ms.keywords: "*PHWPROFILE_CHANGE_NOTIFICATION, HWPROFILE_CHANGE_NOTIFICATION, HWPROFILE_CHANGE_NOTIFICATION structure [Kernel-Mode Driver Architecture], PHWPROFILE_CHANGE_NOTIFICATION, PHWPROFILE_CHANGE_NOTIFICATION structure pointer [Kernel-Mode Driver Architecture], _HWPROFILE_CHANGE_NOTIFICATION, kernel.hwprofile_change_notification, kstruct_b_2e8d0c69-abe9-49a9-96f6-fba3b0020ff8.xml, wdm/HWPROFILE_CHANGE_NOTIFICATION, wdm/PHWPROFILE_CHANGE_NOTIFICATION"
f1_keywords:
 - "wdm/HWPROFILE_CHANGE_NOTIFICATION"
 - "HWPROFILE_CHANGE_NOTIFICATION"
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
- Wdm.h
api_name:
- HWPROFILE_CHANGE_NOTIFICATION
product:
- Windows
targetos: Windows
req.typenames: HWPROFILE_CHANGE_NOTIFICATION, *PHWPROFILE_CHANGE_NOTIFICATION
---

# _HWPROFILE_CHANGE_NOTIFICATION structure


## -description


The <b>HWPROFILE_CHANGE_NOTIFICATION</b> structure describes an event related to a hardware profile configuration change. The PnP manager sends this structure to a driver that registered a callback routine for notification of <b>EventCategoryHardwareProfileChange</b> events.


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_interface_change_notification">DEVICE_INTERFACE_CHANGE_NOTIFICATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioregisterplugplaynotification">IoRegisterPlugPlayNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_plugplay_notification_header">PLUGPLAY_NOTIFICATION_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_target_device_removal_notification">TARGET_DEVICE_REMOVAL_NOTIFICATION</a>
 

 

