---
UID: NF:wdfdevice.WdfDeviceInitSetPowerPageable
title: WdfDeviceInitSetPowerPageable function
author: windows-driver-content
description: The WdfDeviceInitSetPowerPageable method informs the power manager that the driver must be able to access pageable data while the system is transitioning between a sleeping state and the working (S0) state.
old-location: wdf\wdfdeviceinitsetpowerpageable.htm
tech.root: wdf
ms.assetid: 3a216c35-f6b7-483f-a330-d0a66edb9205
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_704347eb-35c6-4735-bd2a-e6a988ff2896.xml, WdfDeviceInitSetPowerPageable, WdfDeviceInitSetPowerPageable method, kmdf.wdfdeviceinitsetpowerpageable, wdf.wdfdeviceinitsetpowerpageable, wdfdevice/WdfDeviceInitSetPowerPageable
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: ChildDeviceInitAPI, DeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfDeviceInitSetPowerPageable
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceInitSetPowerPageable function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceInitSetPowerPageable</b> method informs the power manager that the driver must be able to access <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-pageable-code-in-a-kmdf-driver">pageable</a> data while the system is transitioning between a sleeping state and the working (S0) state. 


## -parameters




### -param DeviceInit [in]

A caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


## -returns



None




## -remarks



If your function driver or bus driver calls <b>WdfDeviceInitSetPowerPageable</b>, the system ensures that the paging file's device is in its working (D0) state when your driver's device <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/a-device-enters-a-low-power-state">enters a low-power state</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/a-device-returns-to-its-working-state">returns to its working state</a>. This allows your driver to access files, the registry, and paged pool during your device's power transitions. 

By default, the framework enables access to pageable data for function drivers. The framework uses the parent device's setting for each child device that a bus driver enumerates, unless the bus driver calls either <b>WdfDeviceInitSetPowerPageable</b> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff546147">WdfDeviceInitSetPowerNotPageable</a> for the child device. If you write a bus driver that calls <b>WdfDeviceInitSetPowerPageable</b> for a child device, no drivers in the child device's stack can call <b>WdfDeviceInitSetPowerNotPageable</b>. 

Calling <b>WdfDeviceInitSetPowerPageable</b> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff546147">WdfDeviceInitSetPowerNotPageable</a> from a filter driver has no effect. The framework uses the setting that the next-lower driver specifies.

Most drivers do not need to call <b>WdfDeviceInitSetPowerPageable</b> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff546147">WdfDeviceInitSetPowerNotPageable</a>. Instead, you should let the framework use the default setting that is appropriate for your driver. However, your driver should call <b>WdfDeviceInitSetPowerNotPageable</b> if the driver is part of a driver stack that must not access pageable data during power transitions (such as the storage stack or the video stack), or if the driver is a bus driver that enumerates devices that might be storage or video devices. 

If your driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff546142">WdfDeviceInitSetPowerInrush</a>, it must not call <b>WdfDeviceInitSetPowerPageable</b>. 

Your driver must call <b>WdfDeviceInitSetPowerPageable</b> before it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>.

For more information about calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.


#### Examples

The following code example informs the power manager that a driver must be able to access pageable data while the system is transitioning between a sleeping state and the working (S0) state.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfDeviceInitSetPowerPageable(DeviceInit);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546147">WdfDeviceInitSetPowerNotPageable</a>
 

 

