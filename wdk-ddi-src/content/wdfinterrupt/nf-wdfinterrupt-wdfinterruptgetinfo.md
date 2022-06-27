---
UID: NF:wdfinterrupt.WdfInterruptGetInfo
title: WdfInterruptGetInfo function (wdfinterrupt.h)
description: The WdfInterruptGetInfo method retrieves information about a specified interrupt.
old-location: wdf\wdfinterruptgetinfo.htm
tech.root: wdf
ms.date: 01/26/2022
keywords: ["WdfInterruptGetInfo function"]
ms.keywords: DFInterruptObjectRef_eb163aa0-1ba3-491d-b215-85c8773dcfc9.xml, WdfInterruptGetInfo, WdfInterruptGetInfo method, kmdf.wdfinterruptgetinfo, wdf.wdfinterruptgetinfo, wdfinterrupt/WdfInterruptGetInfo
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfInterruptGetInfo
 - wdfinterrupt/WdfInterruptGetInfo
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
 - WdfInterruptGetInfo
---

# WdfInterruptGetInfo function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfInterruptGetInfo</b> method retrieves information about a specified interrupt.

## -parameters

### -param Interrupt [in]


A handle to the interrupt object.

### -param Info [in, out]


A pointer to a caller-allocated <a href="/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_info">WDF_INTERRUPT_INFO</a> structure that has been initialized by calling <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdf_interrupt_info_init">WDF_INTERRUPT_INFO_INIT</a>.

## -remarks

A bug check occurs if the driver supplies an invalid object handle.



The <b>WdfInterruptGetInfo</b> method can obtain interrupt information only if your driver calls it after the framework has called the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a> callback function and before the framework has called the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware">EvtDeviceReleaseHardware</a> callback function. 

After <b>WdfInterruptGetInfo</b> has returned, the driver can identify passive level interrupt objects by examining the <b>Irql</b> member of the  <a href="/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_info">WDF_INTERRUPT_INFO</a> structure. For passive level interrupt objects, this value is PASSIVE_LEVEL.

For information about the order in which a driver's callback functions are called, see <a href="/windows-hardware/drivers/wdf/pnp-and-power-management-scenarios">PnP and Power Management Scenarios</a>.

For more information about handling interrupts in framework-based drivers, see <a href="/windows-hardware/drivers/wdf/handling-hardware-interrupts">Handling Hardware Interrupts</a>.


#### Examples

The following code example initializes a <a href="/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_info">WDF_INTERRUPT_INFO</a> structure and calls <b>WdfInterruptGetInfo</b>.

```cpp
WDF_INTERRUPT_INFO  Info;

WDF_INTERRUPT_INFO_INIT(&Info);
WdfInterruptGetInfo(
                    Interrupt,
                    &Info
                    );
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware">EvtDeviceReleaseHardware</a>



<a href="/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_info">WDF_INTERRUPT_INFO</a>



<a href="/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdf_interrupt_info_init">WDF_INTERRUPT_INFO_INIT</a>
