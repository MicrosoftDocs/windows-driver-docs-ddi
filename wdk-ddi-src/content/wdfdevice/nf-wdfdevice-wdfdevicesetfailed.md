---
UID: NF:wdfdevice.WdfDeviceSetFailed
title: WdfDeviceSetFailed function (wdfdevice.h)
description: The WdfDeviceSetFailed method informs the framework that the driver encountered a hardware or software error that is associated with a specified device.
old-location: wdf\wdfdevicesetfailed.htm
tech.root: wdf
ms.assetid: 87fbceab-d08c-4da7-a257-1454f84c04b7
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_7efacd41-7c8c-4832-b10a-cc7d3dac8982.xml, WdfDeviceSetFailed, WdfDeviceSetFailed method, kmdf.wdfdevicesetfailed, wdf.wdfdevicesetfailed, wdfdevice/WdfDeviceSetFailed
ms.topic: function
f1_keywords:
 - "wdfdevice/WdfDeviceSetFailed"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfDeviceSetFailed
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceSetFailed function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceSetFailed</b> method informs the framework that the driver encountered a hardware or software error that is associated with a specified device.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param FailedAction [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/ne-wdfdevice-_wdf_device_failed_action">WDF_DEVICE_FAILED_ACTION</a>-typed enumerator that indicates whether the framework should attempt to reload the specified device's drivers.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



If a driver encounters an unrecoverable hardware or software error, it must call <b>WdfDeviceSetFailed</b> so that the system can unload the device's drivers.

Starting in UMDF version 2.15, a UMDF driver can request that the underlying bus driver re-enumerate it by calling <b>WdfDeviceSetFailed</b> with <i>FailedAction</i> set to <b>WdfDeviceFailedAttemptRestart</b>. The bus driver must support the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff546570(v=vs.85)">GUID_REENUMERATE_SELF_INTERFACE_STANDARD</a> interface.

Alternatively, a UMDF driver can set <i>FailedAction</i> to <b>WdfDeviceFailedNoRestart</b>.

For more information about <b>WdfDeviceSetFailed</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.


#### Examples

The following code example informs the framework that a failure has occurred. If the specified device's drivers are not supporting other devices, the framework will unload the drivers and then attempt to reload them.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfDeviceSetFailed(
                   device,
                   WdfDeviceFailedAttemptRestart
                   );</pre>
</td>
</tr>
</table></span></div>


