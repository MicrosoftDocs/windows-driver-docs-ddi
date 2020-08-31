---
UID: NF:wdm.PoFxCompleteDevicePowerNotRequired
title: PoFxCompleteDevicePowerNotRequired function (wdm.h)
description: The PoFxCompleteDevicePowerNotRequired routine notifies the power management framework (PoFx) that the calling driver has completed its response to a call to the driver's DevicePowerNotRequiredCallback callback routine.
old-location: kernel\pofxcompletedevicepowernotrequired.htm
tech.root: kernel
ms.assetid: 7DCAFA7C-6F13-4020-BCB6-D36EE164BDAA
ms.date: 04/30/2018
keywords: ["PoFxCompleteDevicePowerNotRequired function"]
ms.keywords: PoFxCompleteDevicePowerNotRequired, PoFxCompleteDevicePowerNotRequired routine [Kernel-Mode Driver Architecture], kernel.pofxcompletedevicepowernotrequired, wdm/PoFxCompleteDevicePowerNotRequired
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: Ntoskrnl.lib
req.dll: Ntoskrnl.exe
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PoFxCompleteDevicePowerNotRequired
 - wdm/PoFxCompleteDevicePowerNotRequired
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Ntoskrnl.exe
api_name:
 - PoFxCompleteDevicePowerNotRequired
---

# PoFxCompleteDevicePowerNotRequired function


## -description

The <b>PoFxCompleteDevicePowerNotRequired</b> routine notifies the power management framework (PoFx) that the calling driver has completed its response to a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_device_power_not_required_callback">DevicePowerNotRequiredCallback</a> callback routine.

## -parameters

### -param Handle 

[in]
A handle that represents the registration of the device with PoFx. The device driver previously received this handle from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregisterdevice">PoFxRegisterDevice</a> routine.

## -remarks

After PoFx calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_device_power_not_required_callback">DevicePowerNotRequiredCallback</a> callback routine, the driver must respond by calling <b>PoFxCompleteDevicePowerNotRequired</b>.

PoFx calls the driver's <i>DevicePowerNotRequiredCallback</i> routine to inform the driver that the device is no longer required to remain in the D0 state. In response to this call, the driver can choose to enter a low-power Dx state or to remain in the D0 state. After the driver has completed its response to the <i>DevicePowerNotRequiredCallback</i> call, the driver calls <b>PoFxCompleteDevicePowerNotRequired</b> to inform PoFx. The <b>PoFxCompleteDevicePowerNotRequired</b> call can occur either during or after the <i>DevicePowerNotRequiredCallback</i> call.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_device_power_not_required_callback">DevicePowerNotRequiredCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregisterdevice">PoFxRegisterDevice</a>

