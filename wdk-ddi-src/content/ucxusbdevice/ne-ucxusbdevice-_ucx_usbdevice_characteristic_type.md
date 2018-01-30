---
UID: NE:ucxusbdevice._UCX_USBDEVICE_CHARACTERISTIC_TYPE
title: "_UCX_USBDEVICE_CHARACTERISTIC_TYPE"
author: windows-driver-content
description: Defines values that indicates the type of device characteristic.
old-location: buses\ucx_usbdevice_characteristic_type.htm
old-project: usbref
ms.assetid: 86FA72CC-C23F-40B9-9FDD-80C3B0D5EA73
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PUCX_USBDEVICE_CHARACTERISTIC_TYPE, ucxusbdevice/PUCX_USBDEVICE_CHARACTERISTIC_TYPE, UCX_USBDEVICE_CHARACTERISTIC_TYPE, buses.ucx_usbdevice_characteristic_type, ucxusbdevice/UCX_USBDEVICE_CHARACTERISTIC_TYPE_PATH_DELAY, PUCX_USBDEVICE_CHARACTERISTIC_TYPE enumeration pointer [Buses], _UCX_USBDEVICE_CHARACTERISTIC_TYPE, UCX_USBDEVICE_CHARACTERISTIC_TYPE_PATH_DELAY, UCX_USBDEVICE_CHARACTERISTIC_TYPE enumeration [Buses], ucxusbdevice/UCX_USBDEVICE_CHARACTERISTIC_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
req.irql: DISPATCH_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ucxusbdevice.h
apiname:
-	UCX_USBDEVICE_CHARACTERISTIC_TYPE
product: Windows
targetos: Windows
req.typenames: UCX_USBDEVICE_CHARACTERISTIC_TYPE
req.product: Windows 10 or later.
---

# _UCX_USBDEVICE_CHARACTERISTIC_TYPE enumeration


## -description


Defines values that indicates the type of device characteristic.


## -syntax


````
typedef enum _UCX_USBDEVICE_CHARACTERISTIC_TYPE { 
  UCX_USBDEVICE_CHARACTERISTIC_TYPE_PATH_DELAY  = 0x01
} UCX_USBDEVICE_CHARACTERISTIC_TYPE, *PUCX_USBDEVICE_CHARACTERISTIC_TYPE;
````


## -enum-fields




### -field UCX_USBDEVICE_CHARACTERISTIC_TYPE_PATH_DELAY

The type of characteristic of the device.


## -see-also

<a href="..\ucxusbdevice\ns-ucxusbdevice-_ucx_usbdevice_characteristic.md">UCX_USBDEVICE_CHARACTERISTIC</a>

<a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_get_characteristic.md">EVT_UCX_USBDEVICE_GET_CHARACTERISTIC</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCX_USBDEVICE_CHARACTERISTIC_TYPE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

