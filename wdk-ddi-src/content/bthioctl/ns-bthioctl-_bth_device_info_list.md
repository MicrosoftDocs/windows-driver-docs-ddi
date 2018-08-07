---
UID: NS:bthioctl._BTH_DEVICE_INFO_LIST
title: "_BTH_DEVICE_INFO_LIST"
author: windows-driver-content
description: The BTH_DEVICE_INFO_LIST structure contains output information about all cached, previously discovered remote devices.
old-location: bltooth\bth_device_info_list.htm
tech.root: bltooth
ms.assetid: ad4888fc-3d90-4920-bf84-aea18841d238
ms.author: windowsdriverdev
ms.date: 4/27/2018
ms.keywords: "*PBTH_DEVICE_INFO_LIST, BTH_DEVICE_INFO_LIST, BTH_DEVICE_INFO_LIST structure [Bluetooth Devices], PBTH_DEVICE_INFO_LIST, PBTH_DEVICE_INFO_LIST structure pointer [Bluetooth Devices], _BTH_DEVICE_INFO_LIST, bltooth.bth_device_info_list, bth_structs_230962ed-c458-4c9e-a317-e2508b07c059.xml, bthioctl/BTH_DEVICE_INFO_LIST, bthioctl/PBTH_DEVICE_INFO_LIST"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthioctl.h
req.include-header: Bthioctl.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthioctl.h
api_name:
-	BTH_DEVICE_INFO_LIST
product:
- Windows
targetos: Windows
req.typenames: BTH_DEVICE_INFO_LIST, *PBTH_DEVICE_INFO_LIST
---

# _BTH_DEVICE_INFO_LIST structure


## -description


The BTH_DEVICE_INFO_LIST structure contains output information about all cached, previously
  discovered remote devices.


## -struct-fields




### -field numOfDevices

The number of devices that have been discovered.


### -field deviceList

An open-ended array of 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=50713">BTH_DEVICE_INFO</a> structures. Each
     structure contains information about a previously discovered remote device.


## -remarks



The 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536683">IOCTL_BTH_GET_DEVICE_INFO</a> call's
    output buffer contains the list of all cached, previously discovered remote devices.

The 
    <b>numOfDevices</b> member of the BTH_DEVICE_INFO_LIST structure returns the total number of
    BTH_DEVICE_INFO structures available. If the calling driver passes in a smaller buffer, only a portion of
    the available structures will be returned.




## -see-also




<a href="http://go.microsoft.com/fwlink/p/?linkid=50713">BTH_DEVICE_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536683">IOCTL_BTH_GET_DEVICE_INFO</a>
 

 

