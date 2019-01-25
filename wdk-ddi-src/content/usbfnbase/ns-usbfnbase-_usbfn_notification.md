---
UID: NS:usbfnbase._USBFN_NOTIFICATION
title: "_USBFN_NOTIFICATION" (usbfnbase.h)
description: Describes information about a Universal Serial Bus (USB) event notification that was received by using IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION.
old-location: buses\usbfn_notification.htm
tech.root: usbref
ms.assetid: 84B66823-F357-44DD-A401-79E27FA6B324
ms.date: 05/07/2018
ms.keywords: "*PUSBFN_NOTIFICATION, PUSBFN_NOTIFICATION, PUSBFN_NOTIFICATION structure pointer [Buses], USBFN_NOTIFICATION, USBFN_NOTIFICATION structure [Buses], _USBFN_NOTIFICATION, buses.usbfn_notification, usbfnbase/PUSBFN_NOTIFICATION, usbfnbase/USBFN_NOTIFICATION"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbfnbase.h
api_name:
-	USBFN_NOTIFICATION
product:
- Windows
targetos: Windows
req.typenames: USBFN_NOTIFICATION, *PUSBFN_NOTIFICATION
---

# _USBFN_NOTIFICATION structure


## -description


Describes information about a Universal Serial Bus (USB)  event notification that was 
		received by using <a href="https://msdn.microsoft.com/library/windows/hardware/mt187892">IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION</a>.
		


## -struct-fields




### -field Event

Bus notification indicated by a <a href="https://msdn.microsoft.com/library/windows/hardware/mt187994">USBFN_EVENT</a>-typed flag.


### -field u


### -field u.BusSpeed

The operating bus speed indicated by <a href="https://msdn.microsoft.com/library/windows/hardware/mt187987">USBFN_BUS_SPEED</a>-typed flags.


### -field u.SetupPacket

Describes a setup packet in a  <b>USB_DEFAULT_PIPE_SETUP_PACKET</b> structure for a control transfer to or from the default endpoint as indicated by a <b>USB_DEFAULT_PIPE_SETUP_PACKET</b>-typed flag.


### -field u.ConfigurationValue

The <b>bConfigurationValue</b> field of a USB configuration descriptor.


### -field u.PortType

Possible port types supported by a function controller indicated by a <a href="https://msdn.microsoft.com/library/windows/hardware/mt188004">USBFN_PORT_TYPE</a>-typed flag.


### -field u.AlternateInterface

Alternate setting of the interface indicated by <a href="https://msdn.microsoft.com/library/windows/hardware/mt187816">ALTERNATE_INTERFACE</a>.

