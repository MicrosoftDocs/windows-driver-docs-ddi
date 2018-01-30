---
UID: NS:bthioctl._BTH_DEVICE_INFO_LIST
title: "_BTH_DEVICE_INFO_LIST"
author: windows-driver-content
description: The BTH_DEVICE_INFO_LIST structure contains output information about all cached, previously discovered remote devices.
old-location: bltooth\bth_device_info_list.htm
old-project: bltooth
ms.assetid: ad4888fc-3d90-4920-bf84-aea18841d238
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: "_BTH_DEVICE_INFO_LIST, BTH_DEVICE_INFO_LIST, PBTH_DEVICE_INFO_LIST, bthioctl/PBTH_DEVICE_INFO_LIST, bthioctl/BTH_DEVICE_INFO_LIST, BTH_DEVICE_INFO_LIST structure [Bluetooth Devices], bth_structs_230962ed-c458-4c9e-a317-e2508b07c059.xml, PBTH_DEVICE_INFO_LIST structure pointer [Bluetooth Devices], bltooth.bth_device_info_list, *PBTH_DEVICE_INFO_LIST"
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
req.irql: "<= PASSIVE_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	bthioctl.h
apiname:
-	BTH_DEVICE_INFO_LIST
product: Windows
targetos: Windows
req.typenames: "*PBTH_DEVICE_INFO_LIST, BTH_DEVICE_INFO_LIST"
---

# _BTH_DEVICE_INFO_LIST structure


## -description


The BTH_DEVICE_INFO_LIST structure contains output information about all cached, previously
  discovered remote devices.


## -syntax


````
typedef struct _BTH_DEVICE_INFO_LIST {
  ULONG           numOfDevices;
  BTH_DEVICE_INFO deviceList[1];
} BTH_DEVICE_INFO_LIST, *PBTH_DEVICE_INFO_LIST;
````


## -struct-fields




### -field numOfDevices

The number of devices that have been discovered.


### -field deviceList

An open-ended array of 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=50713">BTH_DEVICE_INFO</a> structures. Each
     structure contains information about a previously discovered remote device.


## -remarks


The 
    <a href="..\bthioctl\ni-bthioctl-ioctl_bth_get_device_info.md">IOCTL_BTH_GET_DEVICE_INFO</a> call's
    output buffer contains the list of all cached, previously discovered remote devices.

The 
    <b>numOfDevices</b> member of the BTH_DEVICE_INFO_LIST structure returns the total number of
    BTH_DEVICE_INFO structures available. If the calling driver passes in a smaller buffer, only a portion of
    the available structures will be returned.



## -see-also

<a href="..\bthioctl\ni-bthioctl-ioctl_bth_get_device_info.md">IOCTL_BTH_GET_DEVICE_INFO</a>

<a href="http://go.microsoft.com/fwlink/p/?linkid=50713">BTH_DEVICE_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20BTH_DEVICE_INFO_LIST structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

