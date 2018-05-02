---
UID: NC:usbbusif.PUSB_BUSIFFN_GETUSBDI_VERSION
title: PUSB_BUSIFFN_GETUSBDI_VERSION
author: windows-driver-content
description: The GetUSBDIVersion routine returns the USB interface version number and the version number of the USB specification that defines the interface, along with information about host controller capabilities.
old-location: buses\getusbdiversion.htm
old-project: usbref
ms.assetid: 05a22049-5165-41a3-aa6f-134c5d1b6c15
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: GetUSBDIVersion, GetUSBDIVersion callback function [Buses], PUSB_BUSIFFN_GETUSBDI_VERSION, USB_BUSIFFN_GETUSBDI_VERSION, USB_BUSIFFN_GETUSBDI_VERSION callback, buses.getusbdiversion, usbbusif/GetUSBDIVersion, usbinterKR_48f5b2a5-9cd8-46c2-abf9-313469817541.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	usbbusif.h
api_name:
-	GetUSBDIVersion
product:
- Windows
targetos: Windows
req.typenames: 
---

# PUSB_BUSIFFN_GETUSBDI_VERSION callback function


## -description


The <b>GetUSBDIVersion</b> routine returns the USB interface version number and the version number of the USB specification that defines the interface, along with information about host controller capabilities. 
<div class="alert"><b>Note</b>  <a href="https://msdn.microsoft.com/library/windows/hardware/hh406233">USBD_IsInterfaceVersionSupported</a> replaces the <b>GetUSBDIVersion</b>  routine. To determine the capabilities of the host controller and the underlying USB driver stack, call <a href="https://msdn.microsoft.com/library/windows/hardware/hh406230">USBD_QueryUsbCapability</a>.</div><div> </div>

## -parameters












#### - BusContext [in]

Handle returned in the <b>BusContext</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539210">USB_BUS_INTERFACE_USBDI_V0</a> structure by an IRP_MN_QUERY_INTERFACE request. 


#### - HcdCapabilities [out, optional]

Returns the host capability flags. Currently, no host capability flags are reported.


#### - VersionInformation [out, optional]

Returns a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539149">USBD_VERSION_INFORMATION</a> structure that contains the USB interface version number and the USB specification version number. 


## -returns



This callback function does not return a value.




## -remarks



The function returns the highest USBDI Interface Version supported by the port driver. This function replaces the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539063">USBD_GetUSBDIVersion</a> library function provided by usbd.sys. 

The function definition that is provided on this reference page is an example function whose parameters are just placeholder names. The actual prototype of the function is declared in usbbusif.h as follows:

<pre class="syntax" xml:space="preserve"><code>typedef VOID
  (USB_BUSIFFN *PUSB_BUSIFFN_GETUSBDI_VERSION) (
    IN PVOID,
    IN OUT PUSBD_VERSION_INFORMATION,
    IN OUT PULONG 
  );</code></pre>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539063">USBD_GetUSBDIVersion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539149">USBD_VERSION_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539210">USB_BUS_INTERFACE_USBDI_V0</a>
 

 

