---
UID: NC:usbbusif.PUSB_BUSIFFN_GETUSBDI_VERSION
title: USB_BUSIFFN_GETUSBDI_VERSION
author: windows-driver-content
description: The GetUSBDIVersion routine returns the USB interface version number and the version number of the USB specification that defines the interface, along with information about host controller capabilities.
old-location: buses\getusbdiversion.htm
old-project: usbref
ms.assetid: 05a22049-5165-41a3-aa6f-134c5d1b6c15
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: GetUSBDIVersion, GetUSBDIVersion callback function [Buses], PUSB_BUSIFFN_GETUSBDI_VERSION, USB_BUSIFFN_GETUSBDI_VERSION, buses.getusbdiversion, usbbusif/GetUSBDIVersion, usbinterKR_48f5b2a5-9cd8-46c2-abf9-313469817541.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: usbbusif.h
req.include-header: Usbbusif.h
req.target-type: Desktop
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
req.irql: "< = DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	usbbusif.h
apiname:
-	GetUSBDIVersion
product: Windows
targetos: Windows
req.typenames: USBD_VERSION_INFORMATION, *PUSBD_VERSION_INFORMATION
req.product: Windows 10 or later.
---

# PUSB_BUSIFFN_GETUSBDI_VERSION callback


## -description


The <b>GetUSBDIVersion</b> routine returns the USB interface version number and the version number of the USB specification that defines the interface, along with information about host controller capabilities. 
<div class="alert"><b>Note</b>  <a href="..\usbdlib\nf-usbdlib-usbd_isinterfaceversionsupported.md">USBD_IsInterfaceVersionSupported</a> replaces the <b>GetUSBDIVersion</b>  routine. To determine the capabilities of the host controller and the underlying USB driver stack, call <a href="..\usbdlib\nf-usbdlib-usbd_queryusbcapability.md">USBD_QueryUsbCapability</a>.</div><div> </div>

## -prototype


````
USB_BUSIFFN_GETUSBDI_VERSION GetUSBDIVersion;

VOID GetUSBDIVersion(
  _In_      PVOID                     BusContext,
  _Out_opt_ PUSBD_VERSION_INFORMATION VersionInformation,
  _Out_opt_ PULONG                    HcdCapabilities
)
{ ... }
````


## -parameters












#### - BusContext [in]

Handle returned in the <b>BusContext</b> member of the <a href="..\usbbusif\ns-usbbusif-_usb_bus_interface_usbdi_v0.md">USB_BUS_INTERFACE_USBDI_V0</a> structure by an IRP_MN_QUERY_INTERFACE request. 


#### - HcdCapabilities [out, optional]

Returns the host capability flags. Currently, no host capability flags are reported.


#### - VersionInformation [out, optional]

Returns a pointer to a <a href="..\usb\ns-usb-_usbd_version_information.md">USBD_VERSION_INFORMATION</a> structure that contains the USB interface version number and the USB specification version number. 


## -returns



This callback function does not return a value.




## -remarks



The function returns the highest USBDI Interface Version supported by the port driver. This function replaces the <a href="..\usbdlib\nf-usbdlib-usbd_getusbdiversion.md">USBD_GetUSBDIVersion</a> library function provided by usbd.sys. 

The function definition that is provided on this reference page is an example function whose parameters are just placeholder names. The actual prototype of the function is declared in usbbusif.h as follows:

<pre class="syntax" xml:space="preserve"><code>typedef VOID
  (USB_BUSIFFN *PUSB_BUSIFFN_GETUSBDI_VERSION) (
    IN PVOID,
    IN OUT PUSBD_VERSION_INFORMATION,
    IN OUT PULONG 
  );</code></pre>



## -see-also

<a href="..\usbbusif\ns-usbbusif-_usb_bus_interface_usbdi_v0.md">USB_BUS_INTERFACE_USBDI_V0</a>



<a href="..\usbdlib\nf-usbdlib-usbd_getusbdiversion.md">USBD_GetUSBDIVersion</a>



<a href="..\usb\ns-usb-_usbd_version_information.md">USBD_VERSION_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_BUSIFFN_GETUSBDI_VERSION callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

