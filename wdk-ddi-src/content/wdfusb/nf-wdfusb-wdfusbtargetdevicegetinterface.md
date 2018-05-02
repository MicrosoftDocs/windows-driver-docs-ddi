---
UID: NF:wdfusb.WdfUsbTargetDeviceGetInterface
title: WdfUsbTargetDeviceGetInterface function
author: windows-driver-content
description: The WdfUsbTargetDeviceGetInterface method returns a handle to the framework USB interface object that is associated with a specified interface index.
old-location: wdf\wdfusbtargetdevicegetinterface.htm
old-project: wdf
ms.assetid: 2c7d31a3-081a-420a-ab61-33700155d858
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFUsbRef_b2c7b272-fe4a-4422-9e98-e756cdf3f264.xml, WdfUsbTargetDeviceGetInterface, WdfUsbTargetDeviceGetInterface method, kmdf.wdfusbtargetdevicegetinterface, wdf.wdfusbtargetdevicegetinterface, wdfusb/WdfUsbTargetDeviceGetInterface
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
-	WdfUsbTargetDeviceGetInterface
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetDeviceGetInterface function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetDeviceGetInterface</b> method returns a handle to the framework USB interface object that is associated with a specified interface index.


## -parameters




### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/hh439428">WdfUsbTargetDeviceCreateWithParameters</a>.


### -param InterfaceIndex [in]

A zero-based index value that specifies a USB interface object in the current configuration. This index value might not be the same as the interface number that the USB specification defines.


## -returns



<b>WdfUsbTargetDeviceGetInterface</b> returns a handle to a USB interface object. If the <i>InterfaceIndex</i> value is invalid, this method returns <b>NULL</b>. 

A bug check occurs if a driver-supplied object handle is invalid.




## -remarks



For more information about the <b>WdfUsbTargetDeviceGetInterface</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example obtains a handle to the first USB interface object that the framework has created for a USB device. The example then obtains the number of endpoints that are associated with the interface object.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDFUSBINTERFACE  UsbInterface;
BYTE  numEndpoints;

UsbInterface = WdfUsbTargetDeviceGetInterface(
                                              deviceContext-&gt;UsbTargetDevice,
                                              0
                                              );
numEndpoints = WdfUsbInterfaceGetNumEndpoints(
                                              UsbInterface,
                                              0
                                              );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439428">WdfUsbTargetDeviceCreateWithParameters</a>
 

 

