---
UID: NC:wdm.PO_FX_DEVICE_POWER_REQUIRED_CALLBACK
title: PO_FX_DEVICE_POWER_REQUIRED_CALLBACK
author: windows-driver-content
description: The DevicePowerRequiredCallback callback routine notifies the device driver that the device must enter and remain in the D0 power state.
old-location: kernel\devicepowerrequiredcallback.htm
old-project: kernel
ms.assetid: AC2110EA-A124-4C01-8270-8D6650F80E0A
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.devicepowerrequiredcallback, DevicePowerRequiredCallback routine [Kernel-Mode Driver Architecture], DevicePowerRequiredCallback, PO_FX_DEVICE_POWER_REQUIRED_CALLBACK, PO_FX_DEVICE_POWER_REQUIRED_CALLBACK, wdm/DevicePowerRequiredCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Called at IRQL <= DISPATCH_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdm.h
apiname:
-	DevicePowerRequiredCallback
product: Windows
targetos: Windows
req.typenames: "*PWDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME"
req.product: Windows 10 or later.
---

# PO_FX_DEVICE_POWER_REQUIRED_CALLBACK callback


## -description


The <i>DevicePowerRequiredCallback</i> callback routine notifies the device driver that the device must enter and remain in the D0 power state.


## -prototype


````
PO_FX_DEVICE_POWER_REQUIRED_CALLBACK DevicePowerRequiredCallback;

VOID DevicePowerRequiredCallback(
  _In_ PVOID Context
)
{ ... }
````


## -parameters




### -param Context [in]

A pointer to the device context. The device driver uses this context to store information about the current power state of the device. The device driver specified this pointer in the <b>DeviceContext</b> member of the <a href="..\wdm\ns-wdm-_po_fx_device_v1.md">PO_FX_DEVICE</a> structure that the driver used to register the device with the power management framework (PoFx). This context is opaque to PoFx.


## -returns


None.



## -remarks


After PoFx calls the driver's <i>DevicePowerRequiredCallback</i> routine, the driver must initiate a transition to the D0 state by sending a D0 IRP (an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a> request) down the device stack, if the device is not already in the D0 state. After the driver completes (and all lower drivers complete) handling of this request, the driver must call the <a href="..\wdm\nf-wdm-pofxreportdevicepoweredon.md">PoFxReportDevicePoweredOn</a> routine. The <b>PoFxReportDevicePoweredOn</b> call notifies PoFx that the device completed its response to the <i>DevicePowerRequiredCallback</i> call. The driver can call <b>PoFxReportDevicePoweredOn</b> during or after the <i>DevicePowerRequiredCallback</i> call.

Each time the <i>DevicePowerRequiredCallback</i> routine is called, the driver must respond by calling <b>PoFxReportDevicePoweredOn</b>. The <b>PoFxReportDevicePoweredOn</b> call can occur either during or after the <i>DevicePowerRequiredCallback</i> call. The driver must call <b>PoFxReportDevicePoweredOn</b> regardless of whether no D0 IRP is required, the D0 IRP request fails, or the dispatched D0 IRP succeeds or fails.

PoFx calls the <i>DevicePowerRequiredCallback</i> routine only if PoFx previously called the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh450946">DevicePowerNotRequiredCallback</a> routine to notify the driver that the device was not required to stay in the D0 state.

The call to the <i>DevicePowerRequiredCallback</i> routine can occur at any time after the driver calls <a href="..\wdm\nf-wdm-pofxcompletedevicepowernotrequired.md">PoFxCompleteDevicePowerNotRequired</a> to complete a <i>DevicePowerNotRequiredCallback</i> callback. The <i>DevicePowerRequiredCallback</i> call does not necessarily occur as a result of an action taken by the driver, such as requesting that a component change to the active condition.



## -see-also

<a href="..\wdm\nf-wdm-pofxreportdevicepoweredon.md">PoFxReportDevicePoweredOn</a>

<a href="..\wdm\nf-wdm-pofxregisterdevice.md">PoFxRegisterDevice</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450946">DevicePowerNotRequiredCallback</a>

<a href="..\wdm\nf-wdm-pofxcompletedevicepowernotrequired.md">PoFxCompleteDevicePowerNotRequired</a>

<a href="..\wdm\ns-wdm-_po_fx_device_v1.md">PO_FX_DEVICE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20DevicePowerRequiredCallback routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

