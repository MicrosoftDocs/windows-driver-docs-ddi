---
UID: NF:wdfdevice.WdfDeviceInitSetPowerNotPageable
title: WdfDeviceInitSetPowerNotPageable function (wdfdevice.h)
description: The WdfDeviceInitSetPowerNotPageable method informs the power manager that the driver will not access pageable data while the system is transitioning between a sleeping state and the working (S0) state.
old-location: wdf\wdfdeviceinitsetpowernotpageable.htm
tech.root: wdf
ms.assetid: c0f39e50-8bf1-4ac9-8610-18915b375797
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_b7acdb97-66a4-497f-b9fb-4335d9147c1a.xml, WdfDeviceInitSetPowerNotPageable, WdfDeviceInitSetPowerNotPageable method, kmdf.wdfdeviceinitsetpowernotpageable, wdf.wdfdeviceinitsetpowernotpageable, wdfdevice/WdfDeviceInitSetPowerNotPageable
ms.topic: function
f1_keywords:
 - "wdfdevice/WdfDeviceInitSetPowerNotPageable"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDeviceInitSetPowerNotPageable
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceInitSetPowerNotPageable function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceInitSetPowerNotPageable</b> method informs the power manager that the driver will not access <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-pageable-code-in-a-kmdf-driver">pageable</a> data while the system is transitioning between a sleeping state and the working (S0) state. 


## -parameters




### -param DeviceInit [in]

A caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure.


## -returns



None




## -remarks



If your function driver or bus driver calls <b>WdfDeviceInitSetPowerNotPageable</b>, the system paging file's device might not be in its working (D0) state when your driver's device <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/a-device-enters-a-low-power-state">enters a low-power state</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/a-device-returns-to-its-working-state">returns to its working state</a>. Therefore, during your device's power transitions, your driver must not perform any operations that might cause the operating system to access the paging file. Such operations include accessing files, the registry, or paged pool. 

By default, the framework enables access to pageable data for function drivers. The framework uses the parent device's setting for each child device that a bus driver enumerates, unless the bus driver calls either <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpowerpageable">WdfDeviceInitSetPowerPageable</a> or <b>WdfDeviceInitSetPowerNotPageable</b> for the child device. If you write a bus driver that calls <b>WdfDeviceInitSetPowerPageable</b> for a child device, no drivers in the child device's stack can call <b>WdfDeviceInitSetPowerNotPageable</b>. 

Calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpowerpageable">WdfDeviceInitSetPowerPageable</a> or <b>WdfDeviceInitSetPowerNotPageable</b> from a filter driver has no effect. The framework uses the setting that the next-lower driver specifies.

Most drivers do not need to call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpowerpageable">WdfDeviceInitSetPowerPageable</a> or <b>WdfDeviceInitSetPowerNotPageable</b>. Instead, you should let the framework use the default setting that is appropriate for your driver. However, your driver should call <b>WdfDeviceInitSetPowerNotPageable</b> if the driver is part of a driver stack that must not access pageable data during power transitions (such as the storage stack or the video stack), or if the driver is a bus driver that enumerates devices that might be storage or video devices. 

If your driver calls <b>WdfDeviceInitSetPowerNotPageable</b>, it must do so before it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>.

For more information about calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.


#### Examples

The following code example informs the power manager that a driver will not access pageable data while the system is transitioning between a sleeping state and the working (S0) state.

```cpp
WdfDeviceInitSetPowerNotPageable(DeviceInit);
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpowerpageable">WdfDeviceInitSetPowerPageable</a>
 

 

