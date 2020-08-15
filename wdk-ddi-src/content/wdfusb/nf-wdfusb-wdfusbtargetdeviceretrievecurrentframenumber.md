---
UID: NF:wdfusb.WdfUsbTargetDeviceRetrieveCurrentFrameNumber
title: WdfUsbTargetDeviceRetrieveCurrentFrameNumber function (wdfusb.h)
description: The WdfUsbTargetDeviceRetrieveCurrentFrameNumber method retrieves the current USB frame number.
old-location: wdf\wdfusbtargetdeviceretrievecurrentframenumber.htm
tech.root: wdf
ms.assetid: 7f73339f-adac-4569-92e7-1b166f93db92
ms.date: 02/26/2018
keywords: ["WdfUsbTargetDeviceRetrieveCurrentFrameNumber function"]
ms.keywords: DFUsbRef_9dd2f1ce-06f7-43a2-8e65-931c03f69c6e.xml, WdfUsbTargetDeviceRetrieveCurrentFrameNumber, WdfUsbTargetDeviceRetrieveCurrentFrameNumber method, kmdf.wdfusbtargetdeviceretrievecurrentframenumber, wdf.wdfusbtargetdeviceretrievecurrentframenumber, wdfusb/WdfUsbTargetDeviceRetrieveCurrentFrameNumber
f1_keywords:
 - "wdfusb/WdfUsbTargetDeviceRetrieveCurrentFrameNumber"
 - "WdfUsbTargetDeviceRetrieveCurrentFrameNumber"
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfUsbTargetDeviceRetrieveCurrentFrameNumber
targetos: Windows
req.typenames: 
---

# WdfUsbTargetDeviceRetrieveCurrentFrameNumber function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfUsbTargetDeviceRetrieveCurrentFrameNumber</b> method retrieves the current USB frame number.


## -parameters




### -param UsbDevice 
[in]
A handle to a USB device object that was obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>.


### -param CurrentFrameNumber 
[out]
A pointer to a location that receives the current 32-bit USB frame number.


## -returns



<b>WdfUsbTargetDeviceRetrieveCurrentFrameNumber</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return one of the following values:

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
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The frame number was unavailable, possibly because lower drivers do not provide frame numbers.

</td>
</tr>
</table>
 

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



For more information about the <b>WdfUsbTargetDeviceRetrieveCurrentFrameNumber</b> method and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.


#### Examples

The following code example calls <b>WdfUsbTargetDeviceRetrieveCurrentFrameNumber</b>. The example obtains a USB device object handle from driver-defined context space.

```cpp
ULONG  frameNumber;
PMY_DEVICE_CONTEXT  pMyDeviceContext;

pMyDeviceContext = GetDeviceContext(Device);

status = WdfUsbTargetDeviceRetrieveCurrentFrameNumber(
                                              pMyDeviceContext->UsbTargetDevice,
                                              &frameNumber
                                              );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>
 

 

