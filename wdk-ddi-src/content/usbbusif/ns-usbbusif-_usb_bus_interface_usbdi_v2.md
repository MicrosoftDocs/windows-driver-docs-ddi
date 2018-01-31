---
UID: NS:usbbusif._USB_BUS_INTERFACE_USBDI_V2
title: "_USB_BUS_INTERFACE_USBDI_V2"
author: windows-driver-content
description: The USB_BUS_INTERFACE_USBDI_V2 structure is provided by the USB hub driver to allow USB clients to make direct calls to the hub driver without allocating IRPs.
old-location: buses\usb_bus_interface_usbdi_v2.htm
old-project: usbref
ms.assetid: c7d9f8b1-a18f-4644-aaee-c019692e62a6
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PUSB_BUS_INTERFACE_USBDI_V2, usbbusif/USB_BUS_INTERFACE_USBDI_V2, usbinterKR_bcb1539a-bd26-421b-b8b3-c135ffe45e57.xml, *PUSB_BUS_INTERFACE_USBDI_V2, PUSB_BUS_INTERFACE_USBDI_V2 structure pointer [Buses], usbbusif/PUSB_BUS_INTERFACE_USBDI_V2, buses.usb_bus_interface_usbdi_v2, _USB_BUS_INTERFACE_USBDI_V2, USB_BUS_INTERFACE_USBDI_V2, USB_BUS_INTERFACE_USBDI_V2 structure [Buses]
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usbbusif.h
apiname:
-	USB_BUS_INTERFACE_USBDI_V2
product: Windows
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V2, *PUSB_BUS_INTERFACE_USBDI_V2
req.product: Windows 10 or later.
---

# _USB_BUS_INTERFACE_USBDI_V2 structure


## -description


The <b>USB_BUS_INTERFACE_USBDI_V2</b> structure is provided by the USB hub driver to allow USB clients to make direct calls to the hub driver without allocating IRPs. 


## -syntax


````
typedef struct _USB_BUS_INTERFACE_USBDI_V2 {
  USHORT                             Size;
  USHORT                             Version;
  PVOID                              BusContext;
  PINTERFACE_REFERENCE               InterfaceReference;
  PINTERFACE_DEREFERENCE             InterfaceDereference;
  PUSB_BUSIFFN_GETUSBDI_VERSION      GetUSBDIVersion;
  PUSB_BUSIFFN_QUERY_BUS_TIME        QueryBusTime;
  PUSB_BUSIFFN_SUBMIT_ISO_OUT_URB    SubmitIsoOutUrb;
  PUSB_BUSIFFN_QUERY_BUS_INFORMATION QueryBusInformation;
  PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED  IsDeviceHighSpeed;
  PUSB_BUSIFFN_ENUM_LOG_ENTRY        EnumLogEntry;
} USB_BUS_INTERFACE_USBDI_V2, *PUSB_BUS_INTERFACE_USBDI_V2;
````


## -struct-fields




#### - Size

Specifies the size in bytes of the buffer that holds the interface pointers. 


#### - Version

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


#### - BusContext

Contains information that describes the USB bus and the USB bus driver that exposes this interface. This is an opaque entity that the caller must pass to the interface routines. 


#### - InterfaceReference

Pointer to a routine that increments the number of references to this interface. For more information about this routine, see <a href="..\wdm\nc-wdm-pinterface_reference.md">InterfaceReference</a>. 


#### - InterfaceDereference

Pointer to a routine that decrements the number of references to this interface. For more information about this routine, see <a href="..\wdm\nc-wdm-pinterface_dereference.md">InterfaceDereference</a>. 


#### - GetUSBDIVersion

Pointer to a routine that returns the USB interface version number, the version number of USB specification that defines the interface, along with host controller capabilities information. This routine returns the highest USBDI interface version supported by the port driver. For more information about this routine, see <a href="https://msdn.microsoft.com/05a22049-5165-41a3-aa6f-134c5d1b6c15">GetUSBDIVersion</a>. 


#### - QueryBusTime

Pointer to a routine that returns the current 32-bit USB frame number. This routine replaces the <b>USBD_QueryBusTime</b> function provided by usbd.sys. For more information about this routine, see <a href="https://msdn.microsoft.com/6a0a1953-070d-4335-a906-4ca3fe8a04e1">QueryBusTime</a>.


#### - SubmitIsoOutUrb

Reserved. Do not use.


#### - QueryBusInformation

Pointer to a routine that retrieves information about the bus. The information that is returned depends on the value of the <b>Level </b>member. If <b>Level</b> is 0, this routine returns bus bandwidth information. If <b>Level</b> is 1, it returns bus bandwidth information and the host controller's symbolic name. This routine replaces the <b>USBD_QueryBusInformation</b> function provided by usbd.sys. For more information about this routine, see <a href="https://msdn.microsoft.com/cc03ae88-89ba-44ff-bfe7-6255f2a2ec5c">QueryBusInformation</a>. 


#### - IsDeviceHighSpeed

Pointer to a routine that determines if the USB device is operating at high speed. This routine returns <b>TRUE</b> if the USB device is operating at high speed USB 2.0 compliant device. Returns <b>FALSE</b> otherwise. For more information about this routine, see <a href="https://msdn.microsoft.com/36e0041d-700f-44db-84b6-3745026cb6f7">IsDeviceHighSpeed</a>. 


#### - EnumLogEntry

Reserved. Do not use.


## -remarks


The <b>IsDeviceHighSpeed</b> routine does not indicate whether a device is capable of high-speed operation, but whether it is in fact operating at high speed. 

The routines in this structure must be callable at IRQL &gt;= DISPATCH_LEVEL. 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>

<a href="https://msdn.microsoft.com/1b571ee0-d47f-40b6-8beb-d57b49ae3ac8">Bus Driver Interface Routines for USB Client Drivers</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_BUS_INTERFACE_USBDI_V2 structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

