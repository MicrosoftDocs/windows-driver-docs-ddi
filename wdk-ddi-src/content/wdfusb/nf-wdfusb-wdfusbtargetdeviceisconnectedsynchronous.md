---
UID: NF:wdfusb.WdfUsbTargetDeviceIsConnectedSynchronous
title: WdfUsbTargetDeviceIsConnectedSynchronous function (wdfusb.h)
description: The WdfUsbTargetDeviceIsConnectedSynchronous method determines if the specified USB device is connected.
old-location: wdf\wdfusbtargetdeviceisconnectedsynchronous.htm
tech.root: wdf
ms.assetid: 1e598f83-01ad-4c3e-8044-a66041f6ad96
ms.date: 02/26/2018
keywords: ["WdfUsbTargetDeviceIsConnectedSynchronous function"]
ms.keywords: DFUsbRef_52c60eb0-7e47-4064-9bb5-f2c7ba2e182a.xml, WdfUsbTargetDeviceIsConnectedSynchronous, WdfUsbTargetDeviceIsConnectedSynchronous method, kmdf.wdfusbtargetdeviceisconnectedsynchronous, wdf.wdfusbtargetdeviceisconnectedsynchronous, wdfusb/WdfUsbTargetDeviceIsConnectedSynchronous
f1_keywords:
 - "wdfusb/WdfUsbTargetDeviceIsConnectedSynchronous"
 - "WdfUsbTargetDeviceIsConnectedSynchronous"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfUsbTargetDeviceIsConnectedSynchronous
targetos: Windows
req.typenames: 
---

# WdfUsbTargetDeviceIsConnectedSynchronous function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfUsbTargetDeviceIsConnectedSynchronous</b> method determines if the specified USB device is connected.


## -parameters




### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>.


## -returns



<b>WdfUsbTargetDeviceIsConnectedSynchronous</b> returns the I/O target's completion status value if the operation succeeds. Otherwise, this method can return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was detected.

</td>
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
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_NOT_CONNECTED or STATUS_DEVICE_DOES_NOT_EXIST</b></dt>
</dl>
</td>
<td width="60%">
The device was not connected.

</td>
</tr>
</table>
 

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



For more information about the <b>WdfUsbTargetDeviceIsConnectedSynchronous</b> method and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.


#### Examples

The following code example determines if a specified USB device is connected.

```cpp
NTSTATUS status;

status = WdfUsbTargetDeviceIsConnectedSynchronous(UsbDevice);
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>
 

 

