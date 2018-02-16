---
UID: NF:wdfusb.WdfUsbTargetDeviceGetIoTarget
title: WdfUsbTargetDeviceGetIoTarget function
author: windows-driver-content
description: The WdfUsbTargetDeviceGetIoTarget method returns a handle to the I/O target object that is associated with a specified USB device.
old-location: wdf\wdfusbtargetdevicegetiotarget.htm
old-project: wdf
ms.assetid: 8c598cb8-083a-459d-b94b-958b7d625c88
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFUSBTARGETDEVICEGETIOTARGET, wdfusb/WdfUsbTargetDeviceGetIoTarget, WdfUsbTargetDeviceGetIoTarget method, DFUsbRef_d65932cf-8891-4687-a784-eb6f794759fd.xml, wdf.wdfusbtargetdevicegetiotarget, WdfUsbTargetDeviceGetIoTarget, kmdf.wdfusbtargetdevicegetiotarget
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
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
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfUsbTargetDeviceGetIoTarget
product: Windows
targetos: Windows
req.typenames: "*PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE"
req.product: Windows 10 or later.
---

# WdfUsbTargetDeviceGetIoTarget function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetDeviceGetIoTarget</b> method returns a handle to the I/O target object that is associated with a specified USB device.


## -syntax


````
WDFIOTARGET WdfUsbTargetDeviceGetIoTarget(
  _In_ WDFUSBDEVICE UsbDevice
);
````


## -parameters




### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>.


## -returns



The <b>WdfUsbTargetDeviceGetIoTarget</b> method returns a handle to an I/O target object.

A bug check occurs if a driver-supplied object handle is invalid.




## -remarks



For more information about the <b>WdfUsbTargetDeviceGetIoTarget</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example creates a request object and verifies that the framework can send a request to the I/O target object that is associated with a specified USB device. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>status = WdfRequestCreate(
                          &amp;attributes,
                          WdfUsbTargetDeviceGetIoTarget(deviceContext-&gt;UsbTargetDevice),
                          &amp;request
                          );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbtargetpipegetiotarget.md">WdfUsbTargetPipeGetIoTarget</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetDeviceGetIoTarget method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

