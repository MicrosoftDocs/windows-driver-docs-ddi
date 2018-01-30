---
UID: NE:usbfnbase._USBFN_DIRECTION
title: "_USBFN_DIRECTION"
author: windows-driver-content
description: Defines the USB data transfer direction types.
old-location: buses\usbfn_direction.htm
old-project: usbref
ms.assetid: C6E1FA5A-993C-4212-9428-0B759C09F5DE
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: "_USBFN_DIRECTION, usbfnbase/USBFN_DIRECTION, UsbfnDirectionRx, USBFN_DIRECTION, usbfnbase/UsbfnDirectionOut, usbfnbase/UsbfnDirectionRx, UsbfnDirectionTx, *PUSBFN_DIRECTION, UsbfnDirectionIn, USBFN_DIRECTION enumeration [Buses], UsbfnDirectionMaximum, buses.usbfn_direction, UsbfnDirectionMinimum, UsbfnDirectionOut, usbfnbase/UsbfnDirectionMaximum, usbfnbase/UsbfnDirectionTx, usbfnbase/UsbfnDirectionIn, usbfnbase/UsbfnDirectionMinimum"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: usbfnbase.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usbfnbase.h
apiname:
-	USBFN_DIRECTION
product: Windows
targetos: Windows
req.typenames: "*PUSBFN_DIRECTION, USBFN_DIRECTION"
req.product: Windows 10 or later.
---

# _USBFN_DIRECTION enumeration


## -description


Defines the USB data transfer direction types.


## -syntax


````
typedef enum _USBFN_DIRECTION { 
  UsbfnDirectionMinimum  = 0x0,
  UsbfnDirectionIn,
  UsbfnDirectionOut,
  UsbfnDirectionTx       = UsbfnDirectionIn,
  UsbfnDirectionRx       = UsbfnDirectionOut,
  UsbfnDirectionMaximum
} USBFN_DIRECTION;
````


## -enum-fields




### -field UsbfnDirectionMinimum

The minimum value in this enumeration.


### -field UsbfnDirectionIn

The transfer is to the host from an endpoint.


### -field UsbfnDirectionOut

The transfer is from the host to the endpoint.


### -field UsbfnDirectionTx

The bus transfer to the host from the device. 


### -field UsbfnDirectionRx

The bus transfer is from the host to the device.


### -field UsbfnDirectionMaximum

The maximum value in this enumeration.

