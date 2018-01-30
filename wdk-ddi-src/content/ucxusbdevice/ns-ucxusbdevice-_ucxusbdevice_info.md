---
UID: NS:ucxusbdevice._UCXUSBDEVICE_INFO
title: "_UCXUSBDEVICE_INFO"
author: windows-driver-content
description: Contains information about the USB device. This structure is passed by UCX in the EVT_UCX_CONTROLLER_USBDEVICE_ADD event callback function.
old-location: buses\_ucxusbdevice_info.htm
old-project: usbref
ms.assetid: E6875195-D6C4-4CEB-8381-8CBA732223A5
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: "_UCXUSBDEVICE_INFO, ucxusbdevice/P_UCXUSBDEVICE_INFO, P_UCXUSBDEVICE_INFO structure pointer [Buses], UCXUSBDEVICE_INFO structure [Buses], P_UCXUSBDEVICE_INFO, buses._ucxusbdevice_info, UCXUSBDEVICE_INFO, ucxusbdevice/_UCXUSBDEVICE_INFO, *PUCXUSBDEVICE_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxusbdevice.h
req.include-header: Ucxusbdevice.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ucxusbdevice.h
apiname:
-	UCXUSBDEVICE_INFO
product: Windows
targetos: Windows
req.typenames: "*PUCXUSBDEVICE_INFO, UCXUSBDEVICE_INFO"
req.product: Windows 10 or later.
---

# _UCXUSBDEVICE_INFO structure


## -description


Contains information about the USB device. This structure is passed by UCX in the <a href="..\ucxcontroller\nc-ucxcontroller-evt_ucx_controller_usbdevice_add.md">EVT_UCX_CONTROLLER_USBDEVICE_ADD</a> event callback function.


## -syntax


````
typedef struct _UCXUSBDEVICE_INFO {
  ULONG                Size;
  USB_DEVICE_SPEED     DeviceSpeed;
  UCXUSBDEVICE         TtHub;
  USB_DEVICE_PORT_PATH PortPath;
} UCXUSBDEVICE_INFO, *P_UCXUSBDEVICE_INFO;
````


## -struct-fields




### -field Size

The size in bytes of this structure.


### -field DeviceSpeed

Defines the device speed of the USB device or hub.


### -field TtHub

A handle to the USB  device object that represents the TT hub.


### -field PortPath

The port path for the USB device or hub.


## -see-also

<a href="..\ucxcontroller\nc-ucxcontroller-evt_ucx_controller_usbdevice_add.md">EVT_UCX_CONTROLLER_USBDEVICE_ADD</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCXUSBDEVICE_INFO structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

