---
UID: NS:usb._USBD_INTERFACE_INFORMATION
title: "_USBD_INTERFACE_INFORMATION"
author: windows-driver-content
description: The USBD_INTERFACE_INFORMATION structure holds information about an interface for a configuration on a USB device.
old-location: buses\usbd_interface_information.htm
old-project: usbref
ms.assetid: dde09937-14fb-423b-8905-8a398a9c5902
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: USBD_INTERFACE_INFORMATION structure [Buses], usb/PUSBD_INTERFACE_INFORMATION, *PUSBD_INTERFACE_INFORMATION, PUSBD_INTERFACE_INFORMATION structure pointer [Buses], PUSBD_INTERFACE_INFORMATION, buses.usbd_interface_information, usb/USBD_INTERFACE_INFORMATION, USBD_INTERFACE_INFORMATION, _USBD_INTERFACE_INFORMATION, usbstrct_1d2a2627-f530-4ccb-8473-0f028ab44acc.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usb.h
req.include-header: Usb.h
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
-	usb.h
apiname:
-	USBD_INTERFACE_INFORMATION
product: Windows
targetos: Windows
req.typenames: USBD_INTERFACE_INFORMATION, *PUSBD_INTERFACE_INFORMATION
req.product: Windows 10 or later.
---

# _USBD_INTERFACE_INFORMATION structure


## -description


The <b>USBD_INTERFACE_INFORMATION</b> structure holds information about an interface for a configuration on a USB device.


## -syntax


````
typedef struct _USBD_INTERFACE_INFORMATION {
  USHORT                Length;
  UCHAR                 InterfaceNumber;
  UCHAR                 AlternateSetting;
  UCHAR                 Class;
  UCHAR                 SubClass;
  UCHAR                 Protocol;
  UCHAR                 Reserved;
  USBD_INTERFACE_HANDLE InterfaceHandle;
  ULONG                 NumberOfPipes;
  USBD_PIPE_INFORMATION Pipes[1];
} USBD_INTERFACE_INFORMATION, *PUSBD_INTERFACE_INFORMATION;
````


## -struct-fields




### -field Length

Specifies the length, in bytes, of this structure.


### -field InterfaceNumber

Specifies the device-defined index identifier for this interface.


### -field AlternateSetting

Specifies a device-defined index identifier that indicates which alternate setting this interface is using, should use, or describes.


### -field Class

Contains a USB-assigned identifier that specifies a USB-defined class that this interface conforms to.


### -field SubClass

Contains a USB-assigned identifier that specifies a USB-defined subclass that this interface conforms to. This code is specific to the code in <b>Class</b>.


### -field Protocol

Contains a USB-assigned identifier that specifies a USB-defined protocol that this interface conforms to. This code is specific to the codes in <b>Class</b> and <b>SubClass</b>.


### -field Reserved

Reserved.


### -field InterfaceHandle

Contains a host controller driver-defined handle that is used to access this interface. This member should be treated as opaque.


### -field NumberOfPipes

Specifies the number of pipes (endpoints) in this interface.


### -field Pipes

Pointer to the first element in the array of <a href="..\usb\ns-usb-_usbd_pipe_information.md">USBD_PIPE_INFORMATION</a> structures. The length of the array depends on the number of endpoints in the interface descriptor.


## -remarks


Members that are part of this structure, but not described here, should be treated as opaque and considered to be reserved for system use.

The reserved members of this structure must be treated as opaque and are reserved for system use.



## -see-also

<a href="..\usb\ns-usb-_usbd_pipe_information.md">USBD_PIPE_INFORMATION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_INTERFACE_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

