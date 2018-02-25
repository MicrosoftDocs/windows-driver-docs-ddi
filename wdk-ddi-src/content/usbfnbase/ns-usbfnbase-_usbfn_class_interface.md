---
UID: NS:usbfnbase._USBFN_CLASS_INTERFACE
title: "_USBFN_CLASS_INTERFACE"
author: windows-driver-content
description: Describes an interface and its endpoints.
old-location: buses\usbfn_class_interface.htm
old-project: UsbRef
ms.assetid: D7173157-D532-4E71-A4E5-55A3B9626DB8
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ",  , *, *PUSBFN_CLASS_INTERFACE, ,, A, B, C, E, F, I, L, N, P, PUSBFN_CLASS_INTERFACE, PUSBFN_CLASS_INTERFACE structure pointer [Buses], R, S, T, U, USBFN_CLASS_INTERFACE, USBFN_CLASS_INTERFACE structure [Buses], _, _USBFN_CLASS_INTERFACE, buses.usbfn_class_interface, usbfnbase/PUSBFN_CLASS_INTERFACE, usbfnbase/USBFN_CLASS_INTERFACE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	USBFN_CLASS_INTERFACE
product: Windows
targetos: Windows
req.typenames: USBFN_CLASS_INTERFACE, *PUSBFN_CLASS_INTERFACE
req.product: Windows 10 or later.
---

# _USBFN_CLASS_INTERFACE structure


## -description


Describes an interface and its endpoints.


## -syntax


````
typedef struct _USBFN_CLASS_INTERFACE {
  UINT8                  InterfaceNumber;
  UINT8                  PipeCount;
  USBFN_PIPE_INFORMATION PipeArr[MAX_NUM_USBFN_PIPES];
} USBFN_CLASS_INTERFACE, *PUSBFN_CLASS_INTERFACE;
````


## -struct-fields




### -field InterfaceNumber

The index number of the interface.


### -field PipeCount

The number of endpoints contained in  the interface.


### -field PipeArr

An array of <a href="..\usbfnbase\ns-usbfnbase-_usbfn_pipe_information.md">USBFN_PIPE_INFORMATION</a> structures that describes the endpoints in the interface.


## -see-also

<a href="..\usbfnbase\ns-usbfnbase-_usbfn_pipe_information.md">USBFN_PIPE_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20USBFN_CLASS_INTERFACE structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

