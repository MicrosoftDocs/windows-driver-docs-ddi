---
UID: NF:wdfdevice.WdfDeviceStopIdle
title: WdfDeviceStopIdle macro
author: windows-driver-content
description: The WdfDeviceStopIdle method informs the framework that the specified device must be placed in its working (D0) power state.
old-location: wdf\wdfdevicestopidle.htm
old-project: wdf
ms.assetid: a394f539-bd66-44e2-a857-d657a123b473
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfdevice/WdfDeviceStopIdle, wdf.wdfdevicestopidle, WdfDeviceStopIdle method, WdfDeviceStopIdle, kmdf.wdfdevicestopidle, DFDeviceObjectGeneralRef_3dbde224-ecdf-429e-9389-9bdb49b16040.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfDeviceStopIdle
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceStopIdle macro


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceStopIdle</b> method informs the framework that the specified device must be placed in its working (D0) power state.


## -syntax


````
NTSTATUS WdfDeviceStopIdle(
  _In_ WDFDEVICE Device,
  _In_ BOOLEAN   WaitForD0
);
````


## -parameters




#### - Device [in]

A handle to a framework device object.


#### - WaitForD0 [in]

A Boolean value that indicates when <b>WdfDeviceStopIdle</b> will return. If <b>TRUE</b>, it returns only after the specified device has entered the D0 device power state. If <b>FALSE</b>, the method returns immediately.


## -remarks


If your device can enter a low-power state when it becomes idle, your driver might have to occasionally call <b>WdfDeviceStopIdle</b> to bring the device back to its working (D0) state or to prevent it from entering a low-power state. 

Your driver <i>does not</i> have to call <b>WdfDeviceStopIdle</b> when a device is idle and the framework places an I/O request in the device's power-managed I/O queue. Additionally, your driver <i>does not</i> have to call <b>WdfDeviceStopIdle</b> when a device is idle and it detects a wake signal. In both of these cases, the framework requests the bus driver to restore the device's power state to D0.

Although drivers typically do not need to call <b>WdfDeviceStopIdle</b> when handling I/O requests that they obtain from a power-managed I/O queue, the call is allowed. However, drivers must not set the <i>WaitForD0</i> parameter to <b>TRUE</b> when handling I/O requests from a power-managed I/O queue.

Your driver <i>does</i> have to call <b>WdfDeviceStopIdle</b> if it must access the device because of a request that the driver has received outside of a power-managed I/O queue. For example, your driver might support a driver-defined interface or a WMI request that requires accessing the device. In this case, you must ensure that the device is in its working state before the driver accesses the device, and that the device remains in its working state until the driver has finished accessing the device.

Calling <b>WdfDeviceStopIdle</b> forces the device into its working (D0) state, if the system is in its working (S0) state. The device remains in its working state until the driver calls <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceresumeidle.md">WdfDeviceResumeIdle</a>, at which point the framework can place the device in a low-power state if it remains idle.

Do not call <b>WdfDeviceStopIdle</b> before the framework has called the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_entry.md">EvtDeviceD0Entry</a> callback function for the first time.

A call to <b>WdfDeviceStopIdle</b> can restore an idle device to its working state only if the system is in its working (S0) state. If the system is entering a low-power state when a driver calls <b>WdfDeviceStopIdle</b> with the <i>WaitForD0</i> parameter set to <b>TRUE</b>, the function does not return until the system returns to its S0 state.

Every successful call to <b>WdfDeviceStopIdle</b> must eventually be followed by a call to <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceresumeidle.md">WdfDeviceResumeIdle</a>, or else the device will never return to a low-power state if it again becomes idle. Calls to <b>WdfDeviceStopIdle</b> can be nested, so the number of calls to <b>WdfDeviceResumeIdle</b> must equal the number of calls to <b>WdfDeviceStopIdle</b>.  Do not call <b>WdfDeviceResumeIdle</b> if a call to <b>WdfDeviceStopIdle</b> fails.

 If the system enters a low-power state after <b>WdfDeviceStopIdle</b> returns, the device also enters a low-power state. When the system returns to its working (S0) state, the device also returns to its working (D0) state.  The power reference from the call to <b>WdfDeviceStopIdle</b> remains active and prevents the device from entering a low-power state until there is a matching call to  <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceresumeidle.md">WdfDeviceResumeIdle</a>.

For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-idle-power-down">Supporting Idle Power-Down</a>.

If <i>WaitForD0</i> is <b>TRUE</b>, <b>WdfDeviceStopIdle</b> must be called at IRQL = PASSIVE_LEVEL. If <i>WaitForD0</i> is <b>FALSE</b>, this method must be called at IRQL &lt;= DISPATCH_LEVEL.

Calling <a href="https://msdn.microsoft.com/library/windows/hardware/dn932460">WdfDeviceStopIdleWithTag</a> instead of <b>WdfDeviceStopIdle</b> provides additional information (tag value, line number, and file name) that you can view in Microsoft debuggers.  



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn932459">WdfDeviceResumeIdleWithTag</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/dn932460">WdfDeviceStopIdleWithTag</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceresumeidle.md">WdfDeviceResumeIdle</a>

<a href="https://msdn.microsoft.com/25F4EEBB-4733-498C-8704-8E015F81FE06">Debugging Power Reference Leaks in WDF</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceStopIdle method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

