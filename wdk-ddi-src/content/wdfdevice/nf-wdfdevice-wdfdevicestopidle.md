---
UID: NF:wdfdevice.WdfDeviceStopIdle
title: WdfDeviceStopIdle macro (wdfdevice.h)
description: The WdfDeviceStopIdle method informs the framework that the specified device must be placed in its working (D0) power state.
old-location: wdf\wdfdevicestopidle.htm
tech.root: wdf
ms.assetid: a394f539-bd66-44e2-a857-d657a123b473
ms.date: 02/26/2018
keywords: ["WdfDeviceStopIdle macro"]
ms.keywords: DFDeviceObjectGeneralRef_3dbde224-ecdf-429e-9389-9bdb49b16040.xml, WdfDeviceStopIdle, WdfDeviceStopIdle method, kmdf.wdfdevicestopidle, wdf.wdfdevicestopidle, wdfdevice/WdfDeviceStopIdle
f1_keywords:
 - "wdfdevice/WdfDeviceStopIdle"
 - "WdfDeviceStopIdle"
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
req.irql: See Remarks section.
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
- WdfDeviceStopIdle
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceStopIdle macro


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceStopIdle</b> method informs the framework that the specified device must be placed in its working (D0) power state.

## -syntax

```cpp
NTSTATUS WdfDeviceStopIdle(
   _In_ WDFDEVICE Device,
   _In_ BOOLEAN WaitForD0
);
```

## -parameters




### -param Device [in]

A handle to a framework device object.


### -param WaitForD0 [in]

A Boolean value that indicates when <b>WdfDeviceStopIdle</b> will return. If <b>TRUE</b>, it returns only after the specified device has entered the D0 device power state. If <b>FALSE</b>, the method returns immediately.

## -remarks


This macro can return the following values:

**STATUS_PENDING**  The device is being powered up asynchronously.
 
**STATUS_INVALID_DEVICE_STATE**  The driver is not the power policy owner for the device.
 
**STATUS_POWER_STATE_INVALID**  A device failure occurred and the device cannot enter its D0 power state.
 
The method might return other NTSTATUS values.

A bug check occurs if the driver supplies an invalid object handle.

If your device can enter a low-power state when it becomes idle, your driver might have to occasionally call <b>WdfDeviceStopIdle</b> to bring the device back to its working (D0) state or to prevent it from entering a low-power state. 

**WdfDeviceStopIdle** does not prevent the framework from transitioning the device to a sleep state when the system changes to an Sx sleep state. Its only effect is to prevent transitions to Dx sleep states while the system is in the S0 working state.

Your driver <i>does not</i> have to call <b>WdfDeviceStopIdle</b> when a device is idle and the framework places an I/O request in the device's power-managed I/O queue. Additionally, your driver <i>does not</i> have to call <b>WdfDeviceStopIdle</b> when a device is idle and it detects a wake signal. In both of these cases, the framework requests the bus driver to restore the device's power state to D0.

Although drivers typically do not need to call <b>WdfDeviceStopIdle</b> when handling I/O requests that they obtain from a power-managed I/O queue, the call is allowed. However, drivers must not set the <i>WaitForD0</i> parameter to <b>TRUE</b> when handling I/O requests from a power-managed I/O queue.

Your driver <i>does</i> have to call <b>WdfDeviceStopIdle</b> if it must access the device because of a request that the driver has received outside of a power-managed I/O queue. For example, your driver might support a driver-defined interface or a WMI request that requires accessing the device. In this case, you must ensure that the device is in its working state before the driver accesses the device, and that the device remains in its working state until the driver has finished accessing the device.

Calling <b>WdfDeviceStopIdle</b> forces the device into its working (D0) state, if the system is in its working (S0) state. The device remains in its working state until the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceresumeidle">WdfDeviceResumeIdle</a>, at which point the framework can place the device in a low-power state if it remains idle.

Do not call <b>WdfDeviceStopIdle</b> before the framework has called the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_entry">EvtDeviceD0Entry</a> callback function for the first time.

A call to <b>WdfDeviceStopIdle</b> can restore an idle device to its working state only if the system is in its working (S0) state. If the system is transitioning to a low-power state or the device has already been powered down in response to Sx (where x > 0) when a driver calls <b>WdfDeviceStopIdle</b> with the <i>WaitForD0</i> parameter set to <b>TRUE</b>, the function does not return until the system returns to its S0 state.

Every successful call to <b>WdfDeviceStopIdle</b> must eventually be followed by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceresumeidle">WdfDeviceResumeIdle</a>, or else the device will never return to a low-power state if it again becomes idle. Calls to <b>WdfDeviceStopIdle</b> can be nested, so the number of calls to <b>WdfDeviceResumeIdle</b> must equal the number of calls to <b>WdfDeviceStopIdle</b>.  Do not call <b>WdfDeviceResumeIdle</b> if a call to <b>WdfDeviceStopIdle</b> fails.

 If the system enters a low-power state after <b>WdfDeviceStopIdle</b> returns, the device also enters a low-power state. When the system returns to its working (S0) state, the device also returns to its working (D0) state.  The power reference from the call to <b>WdfDeviceStopIdle</b> remains active and prevents the device from entering a low-power state until there is a matching call to  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceresumeidle">WdfDeviceResumeIdle</a>.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-idle-power-down">Supporting Idle Power-Down</a>.

If <i>WaitForD0</i> is <b>TRUE</b>, <b>WdfDeviceStopIdle</b> must be called at IRQL = PASSIVE_LEVEL. If <i>WaitForD0</i> is <b>FALSE</b>, this method must be called at IRQL <= DISPATCH_LEVEL.

Calling <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevicestopidlewithtag">WdfDeviceStopIdleWithTag</a> instead of <b>WdfDeviceStopIdle</b> provides additional information (tag value, line number, and file name) that you can view in Microsoft debuggers.  


#### Examples

In the following code example, <b>WdfDeviceStopIdle</b> returns after the specified device has entered the D0 device power state.

```cpp
NTSTATUS  status;

status = WdfDeviceStopIdle(Device, TRUE);
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/debugging-power-reference-leaks-in-wdf">Debugging Power Reference Leaks in WDF</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceresumeidle">WdfDeviceResumeIdle</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdeviceresumeidlewithtag">WdfDeviceResumeIdleWithTag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevicestopidlewithtag">WdfDeviceStopIdleWithTag</a>
 

 

