---
UID: NF:wdm.PoSetDeviceBusy
tech.root: 
title: PoSetDeviceBusy
ms.date: 07/16/2021
targetos: Windows
description: "Learn more about: PoSetDeviceBusy"
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: Any level
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 2000
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - PoSetDeviceBusy
f1_keywords:
 - PoSetDeviceBusy
 - wdm/PoSetDeviceBusy
dev_langs:
 - c++
---

## -description

The **PoSetDeviceBusy** macro notifies the [power manager](/windows-hardware/drivers/kernel/power-manager) that the device associated with _IdlePointer_ is busy.

## -parameters

### -param IdlePointer [in, out]


Specifies a non-**NULL** idle pointer that was previously returned by [**PoRegisterDeviceForIdleDetection**](../ntifs/nf-ntifs-poregisterdeviceforidledetection.md). Note that **PoRegisterDeviceForIdleDetection** might return a **NULL** pointer. A caller of **PoSetDeviceBusy** must verify that the pointer is non-**NULL** before passing it to **PoSetDeviceBusy**.

## -remarks

> [!NOTE]
> The [**PoSetDeviceBusyEx**](../ntifs/nf-ntifs-posetdevicebusyex.md) routine is a direct replacement for the **PoSetDeviceBusy** macro. If you are writing new driver code for Windows Vista with Service Pack 1 (SP1) and later versions of Windows, call **PoSetDeviceBusyEx** instead of **PoSetDeviceBusy**.

A driver uses **PoSetDeviceBusy** along with **PoRegisterDeviceForIdleDetection** to enable system idle detection for its device. If a device that is registered for idle detection becomes idle, the power manager sends an [**IRP_MN_SET_POWER**](/windows-hardware/drivers/kernel/irp-mn-set-power) request to put the device in a requested sleep state.

**PoSetDeviceBusy** reports that the device is busy, so that the power manager can restart its idle countdown. If the device is not powered up, **PoSetDeviceBusy** does not change its state. That is, it does not cause the system to send a power-on request.

A driver should call **PoSetDeviceBusy** on every I/O request.
