---
UID: NS:wdm._DEVICE_INTERFACE_CHANGE_NOTIFICATION
title: "_DEVICE_INTERFACE_CHANGE_NOTIFICATION"
author: windows-driver-content
description: The DEVICE_INTERFACE_CHANGE_NOTIFICATION structure describes a device interface that has been enabled (arrived) or disabled (removed).
old-location: kernel\device_interface_change_notification.htm
old-project: kernel
ms.assetid: 3b5d67c0-eb3f-4ac1-9f85-f9c673314458
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PDEVICE_INTERFACE_CHANGE_NOTIFICATION, DEVICE_INTERFACE_CHANGE_NOTIFICATION, DEVICE_INTERFACE_CHANGE_NOTIFICATION structure [Kernel-Mode Driver Architecture], PDEVICE_INTERFACE_CHANGE_NOTIFICATION, PDEVICE_INTERFACE_CHANGE_NOTIFICATION structure pointer [Kernel-Mode Driver Architecture], _DEVICE_INTERFACE_CHANGE_NOTIFICATION, kernel.device_interface_change_notification, kstruct_a_43e52fa7-54ee-49bd-b822-4daf39ebcdc2.xml, wdm/DEVICE_INTERFACE_CHANGE_NOTIFICATION, wdm/PDEVICE_INTERFACE_CHANGE_NOTIFICATION"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	DEVICE_INTERFACE_CHANGE_NOTIFICATION
product: Windows
targetos: Windows
req.typenames: DEVICE_INTERFACE_CHANGE_NOTIFICATION, *PDEVICE_INTERFACE_CHANGE_NOTIFICATION
req.product: Windows 10 or later.
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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547073">HWPROFILE_CHANGE_NOTIFICATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549526">IoRegisterPlugPlayNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558805">PLUGPLAY_NOTIFICATION_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564601">TARGET_DEVICE_REMOVAL_NOTIFICATION</a>
 

 

