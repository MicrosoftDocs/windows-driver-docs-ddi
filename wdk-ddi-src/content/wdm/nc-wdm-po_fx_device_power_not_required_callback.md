---
UID: NC:wdm.PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK
title: PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK
author: windows-driver-content
description: The DevicePowerNotRequiredCallback callback routine notifies the device driver that the device is not required to stay in the D0 power state.
old-location: kernel\devicepowernotrequiredcallback.htm
old-project: kernel
ms.assetid: 4BE1EEF7-7053-47AF-91E8-7313C3A56718
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.devicepowernotrequiredcallback, DevicePowerNotRequiredCallback routine [Kernel-Mode Driver Architecture], DevicePowerNotRequiredCallback, PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK, PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK, wdm/DevicePowerNotRequiredCallback
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
-	DevicePowerNotRequiredCallback
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK callback


## -description


The <i>DevicePowerNotRequiredCallback</i> callback routine notifies the device driver that the device is not required to stay in the D0 power state.


## -prototype


````
PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK DevicePowerNotRequiredCallback;

VOID DevicePowerNotRequiredCallback(
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


When PoFx calls the driver's <i>DevicePowerNotRequiredCallback</i> routine, the driver must first decide whether to initiate a transition to a low-power Dx state (by sending an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a> request down the device stack) or to remain in the D0 state. Next, without waiting for any Dx transition to complete, the driver must call the <a href="..\wdm\nf-wdm-pofxcompletedevicepowernotrequired.md">PoFxCompleteDevicePowerNotRequired</a> routine to notify PoFx that the driver completed its response to the <i>DevicePowerNotRequiredCallback</i> callback. The driver can call <b>PoFxCompleteDevicePowerNotRequired</b> before or after the <i>DevicePowerNotRequiredCallback</i> routine returns.

When a device is in the D0 state, and the Fx state or active/idle condition of a component in the device changes, PoFx evaluates whether the device can enter a low-power Dx state or must remain in the D0 state. If the device can enter a low-power Dx state, PoFx calls the driver's <i>DevicePowerNotRequiredCallback</i> routine.

If the device enters a low-power Dx state in response to a <i>DevicePowerNotRequiredCallback</i> callback, but PoFx later determines that the device must enter the D0 state, PoFx calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh450949">DevicePowerRequiredCallback</a> routine. In response to this call, the device must enter the D0 state.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450949">DevicePowerRequiredCallback</a>

<a href="..\wdm\ns-wdm-_po_fx_device_v1.md">PO_FX_DEVICE</a>

<a href="..\wdm\nf-wdm-pofxregisterdevice.md">PoFxRegisterDevice</a>

<a href="..\wdm\nf-wdm-pofxcompletedevicepowernotrequired.md">PoFxCompleteDevicePowerNotRequired</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20DevicePowerNotRequiredCallback routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

