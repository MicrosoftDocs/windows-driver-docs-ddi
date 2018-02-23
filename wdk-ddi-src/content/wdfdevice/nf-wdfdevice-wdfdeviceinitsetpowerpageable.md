---
UID: NF:wdfdevice.WdfDeviceInitSetPowerPageable
title: WdfDeviceInitSetPowerPageable function
author: windows-driver-content
description: The WdfDeviceInitSetPowerPageable method informs the power manager that the driver must be able to access pageable data while the system is transitioning between a sleeping state and the working (S0) state.
old-location: wdf\wdfdeviceinitsetpowerpageable.htm
old-project: wdf
ms.assetid: 3a216c35-f6b7-483f-a330-d0a66edb9205
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WdfDeviceInitSetPowerPageable method, wdf.wdfdeviceinitsetpowerpageable, WdfDeviceInitSetPowerPageable, wdfdevice/WdfDeviceInitSetPowerPageable, kmdf.wdfdeviceinitsetpowerpageable, DFDeviceObjectGeneralRef_704347eb-35c6-4735-bd2a-e6a988ff2896.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfDeviceInitSetPowerPageable
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceInitSetPowerPageable function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceInitSetPowerPageable</b> method informs the power manager that the driver must be able to access <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-pageable-code-in-a-kmdf-driver">pageable</a> data while the system is transitioning between a sleeping state and the working (S0) state. 


## -syntax


````
VOID WdfDeviceInitSetPowerPageable(
  _In_ PWDFDEVICE_INIT DeviceInit
);
````


## -parameters




### -param DeviceInit [in]

A caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


## -returns



None




## -remarks



If your function driver or bus driver calls <b>WdfDeviceInitSetPowerPageable</b>, the system ensures that the paging file's device is in its working (D0) state when your driver's device <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/a-device-enters-a-low-power-state">enters a low-power state</a> or <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/a-device-returns-to-its-working-state">returns to its working state</a>. This allows your driver to access files, the registry, and paged pool during your device's power transitions. 

By default, the framework enables access to pageable data for function drivers. The framework uses the parent device's setting for each child device that a bus driver enumerates, unless the bus driver calls either <b>WdfDeviceInitSetPowerPageable</b> or <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpowernotpageable.md">WdfDeviceInitSetPowerNotPageable</a> for the child device. If you write a bus driver that calls <b>WdfDeviceInitSetPowerPageable</b> for a child device, no drivers in the child device's stack can call <b>WdfDeviceInitSetPowerNotPageable</b>. 

Calling <b>WdfDeviceInitSetPowerPageable</b> or <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpowernotpageable.md">WdfDeviceInitSetPowerNotPageable</a> from a filter driver has no effect. The framework uses the setting that the next-lower driver specifies.

Most drivers do not need to call <b>WdfDeviceInitSetPowerPageable</b> or <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpowernotpageable.md">WdfDeviceInitSetPowerNotPageable</a>. Instead, you should let the framework use the default setting that is appropriate for your driver. However, your driver should call <b>WdfDeviceInitSetPowerNotPageable</b> if the driver is part of a driver stack that must not access pageable data during power transitions (such as the storage stack or the video stack), or if the driver is a bus driver that enumerates devices that might be storage or video devices. 

If your driver calls <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpowerinrush.md">WdfDeviceInitSetPowerInrush</a>, it must not call <b>WdfDeviceInitSetPowerPageable</b>. 

Your driver must call <b>WdfDeviceInitSetPowerPageable</b> before it calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>.

For more information about calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.


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

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpowernotpageable.md">WdfDeviceInitSetPowerNotPageable</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceInitSetPowerPageable method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

