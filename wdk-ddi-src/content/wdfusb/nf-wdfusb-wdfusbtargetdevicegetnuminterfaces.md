---
UID: NF:wdfusb.WdfUsbTargetDeviceGetNumInterfaces
title: WdfUsbTargetDeviceGetNumInterfaces function
author: windows-driver-content
description: The WdfUsbTargetDeviceGetNumInterfaces method returns the number of USB device interfaces that are supported by a specified USB device.
old-location: wdf\wdfusbtargetdevicegetnuminterfaces.htm
old-project: wdf
ms.assetid: d81bdeeb-07de-483d-9803-3577f1076e28
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , D, DFUsbRef_8819241f-cfcd-49de-8775-4f415ab63593.xml, G, I, N, T, U, W, WdfUsbTargetDeviceGetNumInterfaces, WdfUsbTargetDeviceGetNumInterfaces method, a, b, c, d, e, f, g, i, kmdf.wdfusbtargetdevicegetnuminterfaces, m, n, r, s, t, u, v, wdf.wdfusbtargetdevicegetnuminterfaces, wdfusb/WdfUsbTargetDeviceGetNumInterfaces"
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
-	WdfUsbTargetDeviceGetNumInterfaces
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfUsbTargetDeviceGetNumInterfaces function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetDeviceGetNumInterfaces</b> method returns the number of USB device interfaces that are supported by a specified USB device.


## -syntax


````
UCHAR WdfUsbTargetDeviceGetNumInterfaces(
  _In_ WDFUSBDEVICE UsbDevice
);
````


## -parameters




### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>.


## -returns



<b>WdfUsbTargetDeviceGetNumInterfaces</b> returns the number of USB interfaces that the device supports.

A bug check occurs if a driver-supplied object handle is invalid.




## -remarks



For more information about the <b>WdfUsbTargetDeviceGetNumInterfaces</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example obtains the number of USB device interfaces that a specified USB device supports.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>UCHAR numInterfaces;

numInterfaces = WdfUsbTargetDeviceGetNumInterfaces(UsbDevice);</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetDeviceGetNumInterfaces method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

