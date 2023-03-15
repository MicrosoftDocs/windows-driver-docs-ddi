---
UID: NC:ks.PFNKSDEVICEIRPVOID
title: PFNKSDEVICEIRPVOID (ks.h)
description: An AVStream minidriver's IRP handling routine is called when these IRPs are dispatched by the device.IRP_MN_CANCEL_STOP_DEVICEIRP_MN_CANCEL_REMOVE_DEVICEIRP_MN_REMOVE_DEVICEIRP_MN_STOP_DEVICEIRP_MN_SURPRISE_REMOVAL
tech.root: stream
ms.date: 03/06/2023
keywords: ["PFNKSDEVICEIRPVOID callback function"]
ms.keywords: AVStrMiniDeviceCancelStop, MyAVStrMiniDeviceIRP, MyAVStrMiniDeviceIRP routine [Streaming Media Devices], PFNKSDEVICEIRPVOID, avstclbk_5b19ddf6-52f4-4d93-b5e1-7d7b5a41fe8b.xml, ks/MyAVStrMiniDeviceIRP, stream.avstrminidevicecancelstop
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt:
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - PFNKSDEVICEIRPVOID
 - ks/PFNKSDEVICEIRPVOID
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ks.h
api_name:
 - PFNKSDEVICEIRPVOID
---

## -description

An AVStream minidriver's IRP handling routine is called when these IRPs are dispatched by the device.

[IRP_MN_CANCEL_STOP_DEVICE](/windows-hardware/drivers/kernel/irp-mn-cancel-stop-device)

[IRP_MN_CANCEL_REMOVE_DEVICE](/windows-hardware/drivers/kernel/irp-mn-cancel-remove-device)

[IRP_MN_REMOVE_DEVICE](/windows-hardware/drivers/kernel/irp-mn-remove-device)

[IRP_MN_STOP_DEVICE](/windows-hardware/drivers/kernel/irp-mn-stop-device)

[IRP_MN_SURPRISE_REMOVAL](/windows-hardware/drivers/kernel/irp-mn-surprise-removal)

## -parameters

### -param Device [in]

Pointer to the [**KSDEVICE**](./ns-ks-_ksdevice.md) that dispatched the IRP.

### -param Irp [in]

The IRP issued by *Device*.

## -remarks

| IRP | Description |
|---|---|
| [IRP_MN_CANCEL_STOP_DEVICE](/windows-hardware/drivers/kernel/irp-mn-cancel-stop-device) | The minidriver specifies this routine's address in the **CancelStop** member of its [**KSDEVICE_DISPATCH**](./ns-ks-_ksdevice_dispatch.md) structure. This routine is optional. |
| [IRP_MN_CANCEL_REMOVE_DEVICE](/windows-hardware/drivers/kernel/irp-mn-cancel-remove-device) | The minidriver specifies this routine's address in the **CancelRemove** member of its [KSDEVICE_DISPATCH](./ns-ks-_ksdevice_dispatch.md) structure. This routine is called when an [IRP_MN_CANCEL_REMOVE_DEVICE](/windows-hardware/drivers/kernel/irp-mn-cancel-remove-device) is dispatched by the device. This routine is optional. |
| [IRP_MN_REMOVE_DEVICE](/windows-hardware/drivers/kernel/irp-mn-remove-device) | The minidriver specifies this routine's address in the **MiniRemove** member of its [**KSDEVICE_DISPATCH**](./ns-ks-_ksdevice_dispatch.md) structure. AVStream calls this routine when an [IRP_MN_REMOVE_DEVICE](/windows-hardware/drivers/kernel/irp-mn-remove-device) is dispatched by the device. Typically, it will be provided by minidrivers that must free device-associated resources upon device removal. This routine is optional. |
| [IRP_MN_STOP_DEVICE](/windows-hardware/drivers/kernel/irp-mn-stop-device) | The minidriver specifies this routine's address in the **Stop** member of its [**KSDEVICE_DISPATCH**](./ns-ks-_ksdevice_dispatch.md) structure. This is usually provided by minidrivers that need to detach from previously assigned resources before completing a stop operation. This routine is optional. |
| [IRP_MN_SURPRISE_REMOVAL](/windows-hardware/drivers/kernel/irp-mn-surprise-removal) | The minidriver specifies this routine's address in the **SurpriseRemoval** member of its [**KSDEVICE_DISPATCH**](./ns-ks-_ksdevice_dispatch.md) structure. This routine is optional. |

## -see-also

[**KSDEVICE**](./ns-ks-_ksdevice.md)

[**KSDEVICE_DISPATCH**](./ns-ks-_ksdevice_dispatch.md)