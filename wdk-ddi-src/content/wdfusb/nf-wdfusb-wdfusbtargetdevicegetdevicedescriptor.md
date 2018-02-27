---
UID: NF:wdfusb.WdfUsbTargetDeviceGetDeviceDescriptor
title: WdfUsbTargetDeviceGetDeviceDescriptor function
author: windows-driver-content
description: The WdfUsbTargetDeviceGetDeviceDescriptor method retrieves the USB device descriptor for the USB device that is associated with a specified framework USB device object.
old-location: wdf\wdfusbtargetdevicegetdevicedescriptor.htm
old-project: wdf
ms.assetid: b2c70976-00ce-4563-af60-0bbdd1a65540
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFUsbRef_a59d2f05-4ecf-400f-823e-b2d2533020a2.xml, WdfUsbTargetDeviceGetDeviceDescriptor, WdfUsbTargetDeviceGetDeviceDescriptor method, kmdf.wdfusbtargetdevicegetdevicedescriptor, wdf.wdfusbtargetdevicegetdevicedescriptor, wdfusb/WdfUsbTargetDeviceGetDeviceDescriptor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfUsbTargetDeviceGetDeviceDescriptor
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfUsbTargetDeviceGetDeviceDescriptor function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetDeviceGetDeviceDescriptor</b> method retrieves the USB device descriptor for the USB device that is associated with a specified framework USB device object.


## -syntax


````
VOID WdfUsbTargetDeviceGetDeviceDescriptor(
  _In_  WDFUSBDEVICE           UsbDevice,
  _Out_ PUSB_DEVICE_DESCRIPTOR UsbDeviceDescriptor
);
````


## -parameters




### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>.


### -param UsbDeviceDescriptor [out]

A pointer to a caller-allocated <a href="..\usbspec\ns-usbspec-_usb_device_descriptor.md">USB_DEVICE_DESCRIPTOR</a> structure that receives the USB device descriptor.


## -returns



None. 

A bug check occurs if a driver-supplied object handle is invalid.




## -remarks



For more information about the <b>WdfUsbTargetDeviceGetDeviceDescriptor</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example obtains the USB device descriptor for a device. The example stores the descriptor in driver-defined context space.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PMY_DEVICE_CONTEXT  myDeviceContext;

myDeviceContext = GetDeviceContext(device);

WdfUsbTargetDeviceGetDeviceDescriptor(
                                      myDeviceContext-&gt;UsbTargetDevice,
                                      &amp;myDeviceContext-&gt;UsbDeviceDescr
                                      );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\usbspec\ns-usbspec-_usb_device_descriptor.md">USB_DEVICE_DESCRIPTOR</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetDeviceGetDeviceDescriptor method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

