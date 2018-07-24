---
UID: NS:ucxusbdevice._USBDEVICE_PURGEIO
title: "_USBDEVICE_PURGEIO"
author: windows-driver-content
description: The USBDEVICE_PURGEIO structure contains the handle for the Universal Serial Bus (USB) hub or device to purge I/O for.
old-location: buses\_usbdevice_purgeio.htm
tech.root: usbref
ms.assetid: 5E45A5A0-59EE-4A72-9CCA-DD1C9A406EB5
ms.author: windowsdriverdev
ms.date: 5/7/2018
ms.keywords: "*PUSBDEVICE_PURGEIO, P_USBDEVICE_PURGEIO, P_USBDEVICE_PURGEIO structure pointer [Buses], USBDEVICE_PURGEIO, USBDEVICE_PURGEIO structure [Buses], _USBDEVICE_PURGEIO, buses._usbdevice_purgeio, ucxusbdevice/P_USBDEVICE_PURGEIO, ucxusbdevice/_USBDEVICE_PURGEIO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ucxusbdevice.h
api_name:
-	USBDEVICE_PURGEIO
product:
- Windows
targetos: Windows
req.typenames: USBDEVICE_PURGEIO, *PUSBDEVICE_PURGEIO
---

# _USBDEVICE_PURGEIO structure


## -description


The <b>USBDEVICE_PURGEIO</b> structure contains the handle for the Universal Serial Bus (USB) hub or device to purge I/O for.


## -struct-fields




### -field Header

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt188075">USBDEVICE_MGMT_HEADER</a> structure that contains  the handle for the USB hub or device.


### -field OnSuspend

 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt188069">USBDEVICE_ABORTIO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt188078">USBDEVICE_STARTIO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt188079">USBDEVICE_TREE_PURGEIO</a>
 

 

