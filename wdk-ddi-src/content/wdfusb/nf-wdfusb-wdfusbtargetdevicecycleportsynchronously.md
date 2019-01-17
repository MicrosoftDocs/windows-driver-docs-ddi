---
UID: NF:wdfusb.WdfUsbTargetDeviceCyclePortSynchronously
title: WdfUsbTargetDeviceCyclePortSynchronously function
description: The WdfUsbTargetDeviceCyclePortSynchronously method power-cycles the USB port to which a specified device is attached.
old-location: wdf\wdfusbtargetdevicecycleportsynchronously.htm
tech.root: wdf
ms.assetid: 8dee089c-1f1a-4090-8c43-8362bb684139
ms.date: 02/26/2018
ms.keywords: DFUsbRef_9ef45eea-9dd8-4423-add8-0906374ff620.xml, WdfUsbTargetDeviceCyclePortSynchronously, WdfUsbTargetDeviceCyclePortSynchronously method, kmdf.wdfusbtargetdevicecycleportsynchronously, wdf.wdfusbtargetdevicecycleportsynchronously, wdfusb/WdfUsbTargetDeviceCyclePortSynchronously
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfUsbTargetDeviceCyclePortSynchronously
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetDeviceCyclePortSynchronously function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfUsbTargetDeviceCyclePortSynchronously</b> method power-cycles the USB port to which a specified device is attached.


## -parameters




### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/hh439428">WdfUsbTargetDeviceCreateWithParameters</a>.


## -returns



<b>WdfUsbTargetDeviceCyclePortSynchronously</b> returns the I/O target's completion status value if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The caller's IRQL was invalid.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Power-cycling a port causes the device to be surprise-removed and re-enumerated. A driver might request a power cycle after it has loaded firmware into a device.

Before the framework cycles the I/O target's USB port, it cancels all I/O requests that remain in the I/O target's queue. The driver must not send additional I/O requests to the I/O target until <b>WdfUsbTargetDeviceCyclePortSynchronously</b> returns.

The driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548680">WdfIoTargetStop</a> before it calls <b>WdfUsbTargetDeviceCyclePortSynchronously</b>.

For more information about the <b>WdfUsbTargetDeviceCyclePortSynchronously</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example power-cycles a specified device's USB port.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS status;

status = WdfUsbTargetDeviceCyclePortSynchronously(UsbDevice);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439428">WdfUsbTargetDeviceCreateWithParameters</a>
 

 

