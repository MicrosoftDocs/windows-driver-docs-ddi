---
UID: NS:usbbusif._USB_BUS_INTERFACE_USBDI_V2
title: _USB_BUS_INTERFACE_USBDI_V2 (usbbusif.h)
description: The USB_BUS_INTERFACE_USBDI_V2 structure is provided by the USB hub driver to allow USB clients to make direct calls to the hub driver without allocating IRPs.
old-location: buses\usb_bus_interface_usbdi_v2.htm
tech.root: usbref
ms.assetid: c7d9f8b1-a18f-4644-aaee-c019692e62a6
ms.date: 05/07/2018
ms.keywords: "*PUSB_BUS_INTERFACE_USBDI_V2, PUSB_BUS_INTERFACE_USBDI_V2, PUSB_BUS_INTERFACE_USBDI_V2 structure pointer [Buses], USB_BUS_INTERFACE_USBDI_V2, USB_BUS_INTERFACE_USBDI_V2 structure [Buses], _USB_BUS_INTERFACE_USBDI_V2, buses.usb_bus_interface_usbdi_v2, usbbusif/PUSB_BUS_INTERFACE_USBDI_V2, usbbusif/USB_BUS_INTERFACE_USBDI_V2, usbinterKR_bcb1539a-bd26-421b-b8b3-c135ffe45e57.xml"
ms.topic: struct
req.header: usbbusif.h
req.include-header: Usbbusif.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems.
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- usbbusif.h
api_name:
- USB_BUS_INTERFACE_USBDI_V2
product:
- Windows
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V2, *PUSB_BUS_INTERFACE_USBDI_V2
---

# _USB_BUS_INTERFACE_USBDI_V2 structure


## -description


The <b>USB_BUS_INTERFACE_USBDI_V2</b> structure is provided by the USB hub driver to allow USB clients to make direct calls to the hub driver without allocating IRPs. 


## -struct-fields




### -field Size

Specifies the size in bytes of the buffer that holds the interface pointers. 


### -field Version

Indicates, on input, the version of the interface. The values that this member can take are as follows.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
USB_BUSIF_USBDI_VERSION_0

</td>
<td>
Version 0 of the interface.

</td>
</tr>
<tr>
<td>
USB_BUSIF_USBDI_VERSION_1

</td>
<td>
Version 1 of the interface.

</td>
</tr>
<tr>
<td>
USB_BUSIF_USBDI_VERSION_2

</td>
<td>
Version 2 of the interface.

</td>
</tr>
<tr>
<td>
USB_BUSIF_USBDI_VERSION_3

</td>
<td>
Version 3 of the interface.

</td>
</tr>
</table>
 


### -field BusContext

Contains information that describes the USB bus and the USB bus driver that exposes this interface. This is an opaque entity that the caller must pass to the interface routines. 


### -field InterfaceReference

Pointer to a routine that increments the number of references to this interface. For more information about this routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547833">InterfaceReference</a>. 


### -field InterfaceDereference

Pointer to a routine that decrements the number of references to this interface. For more information about this routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547829">InterfaceDereference</a>. 


### -field GetUSBDIVersion

Pointer to a routine that returns the USB interface version number, the version number of USB specification that defines the interface, along with host controller capabilities information. This routine returns the highest USBDI interface version supported by the port driver. For more information about this routine, see <a href="https://msdn.microsoft.com/05a22049-5165-41a3-aa6f-134c5d1b6c15">GetUSBDIVersion</a>. 


### -field QueryBusTime

Pointer to a routine that returns the current 32-bit USB frame number. This routine replaces the <b>USBD_QueryBusTime</b> function provided by usbd.sys. For more information about this routine, see <a href="https://msdn.microsoft.com/6a0a1953-070d-4335-a906-4ca3fe8a04e1">QueryBusTime</a>.


### -field SubmitIsoOutUrb

Reserved. Do not use.


### -field QueryBusInformation

Pointer to a routine that retrieves information about the bus. The information that is returned depends on the value of the <b>Level </b>member. If <b>Level</b> is 0, this routine returns bus bandwidth information. If <b>Level</b> is 1, it returns bus bandwidth information and the host controller's symbolic name. This routine replaces the <b>USBD_QueryBusInformation</b> function provided by usbd.sys. For more information about this routine, see <a href="https://msdn.microsoft.com/cc03ae88-89ba-44ff-bfe7-6255f2a2ec5c">QueryBusInformation</a>. 


### -field IsDeviceHighSpeed

Pointer to a routine that determines if the USB device is operating at high speed. This routine returns <b>TRUE</b> if the USB device is operating at high speed USB 2.0 compliant device. Returns <b>FALSE</b> otherwise. For more information about this routine, see <a href="https://msdn.microsoft.com/36e0041d-700f-44db-84b6-3745026cb6f7">IsDeviceHighSpeed</a>. 


### -field EnumLogEntry

Reserved. Do not use.


## -remarks



The <b>IsDeviceHighSpeed</b> routine does not indicate whether a device is capable of high-speed operation, but whether it is in fact operating at high speed. 

The routines in this structure must be callable at IRQL >= DISPATCH_LEVEL. 




## -see-also




<a href="https://msdn.microsoft.com/1b571ee0-d47f-40b6-8beb-d57b49ae3ac8">Bus Driver Interface Routines for USB Client Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>
 

 

