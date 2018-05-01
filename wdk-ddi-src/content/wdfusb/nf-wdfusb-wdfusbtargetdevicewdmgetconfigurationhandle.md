---
UID: NF:wdfusb.WdfUsbTargetDeviceWdmGetConfigurationHandle
title: WdfUsbTargetDeviceWdmGetConfigurationHandle function
author: windows-driver-content
description: The WdfUsbTargetDeviceWdmGetConfigurationHandle method returns the USBD_CONFIGURATION_HANDLE-typed handle that is associated with the current configuration of a specified USB device.
old-location: wdf\wdfusbtargetdevicewdmgetconfigurationhandle.htm
old-project: wdf
ms.assetid: 7f501e5c-13dd-418d-9b9f-f984aed45cc0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFUsbRef_503d3873-7148-4084-b56e-199b7437511b.xml, WdfUsbTargetDeviceWdmGetConfigurationHandle, WdfUsbTargetDeviceWdmGetConfigurationHandle method, kmdf.wdfusbtargetdevicewdmgetconfigurationhandle, wdf.wdfusbtargetdevicewdmgetconfigurationhandle, wdfusb/WdfUsbTargetDeviceWdmGetConfigurationHandle
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfUsbTargetDeviceWdmGetConfigurationHandle
product: Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetDeviceWdmGetConfigurationHandle function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfUsbTargetDeviceWdmGetConfigurationHandle</b> method returns the USBD_CONFIGURATION_HANDLE-typed handle that is associated with the current configuration of a specified USB device.


## -parameters




### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/hh439428">WdfUsbTargetDeviceCreateWithParameters</a>.


## -returns



If the driver has selected a configuration for the device, <b>WdfUsbTargetDeviceWdmGetConfigurationHandle</b> returns the device's USBD_CONFIGURATION_HANDLE-typed handle. Otherwise, the method returns <b>NULL</b>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



A framework-based driver needs to obtain a USBD_CONFIGURATION_HANDLE-typed handle only if it creates a <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a> that contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540425">_URB_SELECT_INTERFACE</a> structure.

The driver can call <b>WdfUsbTargetDeviceWdmGetConfigurationHandle</b> after it has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff550101">WdfUsbTargetDeviceSelectConfig</a>. The USBD_CONFIGURATION_HANDLE-typed handle that <b>WdfUsbTargetDeviceWdmGetConfigurationHandle</b> returns is valid until the driver calls <b>WdfUsbTargetDeviceSelectConfig</b> again or the USB device object is deleted. If the driver provides an <a href="https://msdn.microsoft.com/aba2efca-7d1f-4594-af65-13356f0e3f8b">EvtCleanupCallback</a> function for the USB device object, and if the object is deleted before the driver calls <b>WdfUsbTargetDeviceSelectConfig</b> again, the handle is valid until the object's <i>EvtCleanupCallback</i> function returns.

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550101">WdfUsbTargetDeviceSelectConfig</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540425">_URB_SELECT_INTERFACE</a>
 

 

