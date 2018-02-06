---
UID: NS:usbfnbase._USBFN_NOTIFICATION
title: "_USBFN_NOTIFICATION"
author: windows-driver-content
description: Describes information about a Universal Serial Bus (USB) event notification that was received by using IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION.
old-location: buses\usbfn_notification.htm
old-project: usbref
ms.assetid: 84B66823-F357-44DD-A401-79E27FA6B324
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: usbfnbase/PUSBFN_NOTIFICATION, buses.usbfn_notification, PUSBFN_NOTIFICATION, USBFN_NOTIFICATION structure [Buses], _USBFN_NOTIFICATION, usbfnbase/USBFN_NOTIFICATION, PUSBFN_NOTIFICATION structure pointer [Buses], *PUSBFN_NOTIFICATION, USBFN_NOTIFICATION
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
-	USBFN_NOTIFICATION
product: Windows
targetos: Windows
req.typenames: USBFN_NOTIFICATION, *PUSBFN_NOTIFICATION
req.product: Windows 10 or later.
---

# _USBFN_NOTIFICATION structure


## -description


Describes information about a Universal Serial Bus (USB)  event notification that was 
		received by using <a href="..\usbfnioctl\ni-usbfnioctl-ioctl_internal_usbfn_bus_event_notification.md">IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION</a>.
		


## -syntax


````
typedef struct _USBFN_NOTIFICATION {
  USBFN_EVENT Event;
  union {
    USBFN_BUS_SPEED               BusSpeed;
    USB_DEFAULT_PIPE_SETUP_PACKET SetupPacket;
    USHORT                        ConfigurationValue;
    USBFN_PORT_TYPE               PortType;
    ALTERNATE_INTERFACE           AlternateInterface;
  } u;
} USBFN_NOTIFICATION, *PUSBFN_NOTIFICATION;
````


## -struct-fields




### -field u



### -field u.BusSpeed

The operating bus speed indicated by <a href="..\usbfnbase\ne-usbfnbase-_usbfn_bus_speed.md">USBFN_BUS_SPEED</a>-typed flags.


### -field u.SetupPacket

Describes a setup packet in a  <b>USB_DEFAULT_PIPE_SETUP_PACKET</b> structure for a control transfer to or from the default endpoint as indicated by a <b>USB_DEFAULT_PIPE_SETUP_PACKET</b>-typed flag.


### -field u.ConfigurationValue

The <b>bConfigurationValue</b> field of a USB configuration descriptor.


### -field u.PortType

Possible port types supported by a function controller indicated by a <a href="..\usbfnbase\ne-usbfnbase-_usbfn_port_type.md">USBFN_PORT_TYPE</a>-typed flag.


### -field u.AlternateInterface

Alternate setting of the interface indicated by <a href="..\usbfnbase\ns-usbfnbase-_alternate_interface.md">ALTERNATE_INTERFACE</a>.


### -field Event

Bus notification indicated by a <a href="..\usbfnbase\ne-usbfnbase-_usbfn_event.md">USBFN_EVENT</a>-typed flag.

