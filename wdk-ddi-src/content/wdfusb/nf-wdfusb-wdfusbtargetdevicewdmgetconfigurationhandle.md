---
UID: NF:wdfusb.WdfUsbTargetDeviceWdmGetConfigurationHandle
title: WdfUsbTargetDeviceWdmGetConfigurationHandle function
author: windows-driver-content
description: The WdfUsbTargetDeviceWdmGetConfigurationHandle method returns the USBD_CONFIGURATION_HANDLE-typed handle that is associated with the current configuration of a specified USB device.
old-location: wdf\wdfusbtargetdevicewdmgetconfigurationhandle.htm
old-project: wdf
ms.assetid: 7f501e5c-13dd-418d-9b9f-f984aed45cc0
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , C, D, DFUsbRef_503d3873-7148-4084-b56e-199b7437511b.xml, G, H, T, U, W, WdfUsbTargetDeviceWdmGetConfigurationHandle, WdfUsbTargetDeviceWdmGetConfigurationHandle method, a, b, c, d, e, f, g, i, kmdf.wdfusbtargetdevicewdmgetconfigurationhandle, l, m, n, o, r, s, t, u, v, wdf.wdfusbtargetdevicewdmgetconfigurationhandle, wdfusb/WdfUsbTargetDeviceWdmGetConfigurationHandle"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfUsbTargetDeviceWdmGetConfigurationHandle
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfUsbTargetDeviceWdmGetConfigurationHandle function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfUsbTargetDeviceWdmGetConfigurationHandle</b> method returns the USBD_CONFIGURATION_HANDLE-typed handle that is associated with the current configuration of a specified USB device.


## -syntax


````
USBD_CONFIGURATION_HANDLE WdfUsbTargetDeviceWdmGetConfigurationHandle(
  _In_ WDFUSBDEVICE UsbDevice
);
````


## -parameters




### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>.


## -returns



If the driver has selected a configuration for the device, <b>WdfUsbTargetDeviceWdmGetConfigurationHandle</b> returns the device's USBD_CONFIGURATION_HANDLE-typed handle. Otherwise, the method returns <b>NULL</b>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



A framework-based driver needs to obtain a USBD_CONFIGURATION_HANDLE-typed handle only if it creates a <a href="..\usb\ns-usb-_urb.md">URB</a> that contains a <a href="..\usb\ns-usb-_urb_select_interface.md">_URB_SELECT_INTERFACE</a> structure.

The driver can call <b>WdfUsbTargetDeviceWdmGetConfigurationHandle</b> after it has called <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceselectconfig.md">WdfUsbTargetDeviceSelectConfig</a>. The USBD_CONFIGURATION_HANDLE-typed handle that <b>WdfUsbTargetDeviceWdmGetConfigurationHandle</b> returns is valid until the driver calls <b>WdfUsbTargetDeviceSelectConfig</b> again or the USB device object is deleted. If the driver provides an <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> function for the USB device object, and if the object is deleted before the driver calls <b>WdfUsbTargetDeviceSelectConfig</b> again, the handle is valid until the object's <i>EvtCleanupCallback</i> function returns.

For more information about the <b>WdfUsbTargetDeviceWdmGetConfigurationHandle</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example obtains a handle to the current configuration of a specified USB device.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>USBD_CONFIGURATION_HANDLE deviceConfigHdl;

deviceConfigHdl = WdfUsbTargetDeviceWdmGetConfigurationHandle(UsbDevice);</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\usb\ns-usb-_urb_select_interface.md">_URB_SELECT_INTERFACE</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceselectconfig.md">WdfUsbTargetDeviceSelectConfig</a>



<a href="..\usb\ns-usb-_urb.md">URB</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetDeviceWdmGetConfigurationHandle method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

