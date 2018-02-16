---
UID: NS:usbbusif._USB_BUS_INTERFACE_USBDI_V0
title: "_USB_BUS_INTERFACE_USBDI_V0"
author: windows-driver-content
description: The USB_BUS_INTERFACE_USBDI_V0 structure is provided by the USB hub driver to allow USB clients to make direct calls to the hub driver without allocating IRPs.
old-location: buses\usb_bus_interface_usbdi_v0.htm
old-project: usbref
ms.assetid: f21ba9f4-9571-4918-8f10-97bd308c69f3
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: buses.usb_bus_interface_usbdi_v0, USB_BUS_INTERFACE_USBDI_V0 structure [Buses], *PUSB_BUS_INTERFACE_USBDI_V0, PUSB_BUS_INTERFACE_USBDI_V0, usbbusif/USB_BUS_INTERFACE_USBDI_V0, usbinterKR_2af580ba-2b3f-4f20-808a-5cd5d42b8ada.xml, USB_BUS_INTERFACE_USBDI_V0, _USB_BUS_INTERFACE_USBDI_V0, PUSB_BUS_INTERFACE_USBDI_V0 structure pointer [Buses], usbbusif/PUSB_BUS_INTERFACE_USBDI_V0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbbusif.h
req.include-header: Usbbusif.h
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
-	usbbusif.h
apiname:
-	USB_BUS_INTERFACE_USBDI_V0
product: Windows
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V0, *PUSB_BUS_INTERFACE_USBDI_V0
req.product: Windows 10 or later.
---

# _USB_BUS_INTERFACE_USBDI_V0 structure


## -description


The <b>USB_BUS_INTERFACE_USBDI_V0</b> structure is provided by the USB hub driver to allow USB clients to make direct calls to the hub driver without allocating IRPs. 


## -syntax


````
typedef struct _USB_BUS_INTERFACE_USBDI_V0 {
  USHORT                             Size;
  USHORT                             Version;
  PVOID                              BusContext;
  PINTERFACE_REFERENCE               InterfaceReference;
  PINTERFACE_DEREFERENCE             InterfaceDereference;
  PUSB_BUSIFFN_GETUSBDI_VERSION      GetUSBDIVersion;
  PUSB_BUSIFFN_QUERY_BUS_TIME        QueryBusTime;
  PUSB_BUSIFFN_SUBMIT_ISO_OUT_URB    SubmitIsoOutUrb;
  PUSB_BUSIFFN_QUERY_BUS_INFORMATION QueryBusInformation;
} USB_BUS_INTERFACE_USBDI_V0, *PUSB_BUS_INTERFACE_USBDI_V0;
````


## -struct-fields




### -field Size

Specifies the size in bytes of the buffer that holds the interface pointers. 


### -field Version

Indicates, on input, the version of the interface. This member should have one of the following values:

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

Pointer to a routine that increments the number of references to this interface. For more information about this routine, see <a href="..\wdm\nc-wdm-pinterface_reference.md">InterfaceReference</a>. 


### -field InterfaceDereference

Pointer to a routine that decrements the number of references to this interface. For more information about this routine, see <a href="..\wdm\nc-wdm-pinterface_dereference.md">InterfaceDereference</a>. 


### -field GetUSBDIVersion

Pointer to a routine that returns the USB interface version number, the version number of USB specification that defines the interface, along with host controller capabilities information. This routine returns the highest USBDI interface version that is supported by the port driver. For more information about this routine, see <a href="https://msdn.microsoft.com/05a22049-5165-41a3-aa6f-134c5d1b6c15">GetUSBDIVersion</a>. 


### -field QueryBusTime

Pointer to a routine that returns the current 32-bit USB frame number. This routine replaces the <b>USBD_QueryBusTime</b> function provided by usbd.sys. For more information about this routine, see <a href="https://msdn.microsoft.com/6a0a1953-070d-4335-a906-4ca3fe8a04e1">QueryBusTime</a>.


### -field SubmitIsoOutUrb

Reserved. Do not use.


### -field QueryBusInformation

Pointer to a routine that returns information about the bus. The information that is returned depends on the value of the <b>Level </b>member. If <b>Level</b> is 0, this routine returns bus bandwidth information. If <b>Level</b> is 1, it returns bus bandwidth information and the host controller's symbolic name. This routine replaces the <b>USBD_QueryBusInformation</b> function provided by usbd.sys. For more information about this routine, see <a href="https://msdn.microsoft.com/cc03ae88-89ba-44ff-bfe7-6255f2a2ec5c">QueryBusInformation</a>. 


## -remarks



For information about how to query for these interfaces, see <a href="https://msdn.microsoft.com/1a916e21-3545-4a4e-8309-ba10b3690d63">Querying for USB Interfaces</a>. Callers of the routines in this structure can be running at IRQL &lt;= DISPATCH_LEVEL. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="https://msdn.microsoft.com/1b571ee0-d47f-40b6-8beb-d57b49ae3ac8">Bus Driver Interface Routines for USB Client Drivers</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_BUS_INTERFACE_USBDI_V0 structure%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

