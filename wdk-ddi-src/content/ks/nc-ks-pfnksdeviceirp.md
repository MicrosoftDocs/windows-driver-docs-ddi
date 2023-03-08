---
UID: NC:ks.PFNKSDEVICEIRP
title: PFNKSDEVICEIRP (ks.h)
description: An AVStream minidriver's IRP handler routine is called when these IRPs is dispatched by the device.IRP_MN_QUERY_REMOVE_DEVICEIRP_MN_QUERY_STOP_DEVICEIRP_MN_QUERY_INTERFACE
tech.root: stream
ms.date: 03/06/2023
keywords: ["PFNKSDEVICEIRP callback function"]
ms.keywords: AVStrMiniDeviceQueryInterface, AVStrMiniDeviceQueryRemove, AVStrMiniDeviceQueryRemove routine [Streaming Media Devices], PFNKSDEVICEIRP, avstclbk_e4e3e23a-c4e7-47fb-ad10-6a0a630669ed.xml, ks/AVStrMiniDeviceQueryRemove, stream.avstrminidevicequeryremove
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
req.irql: PASSIVE_LEVEL (See Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - PFNKSDEVICEIRP
 - ks/PFNKSDEVICEIRP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ks.h
api_name:
 - PFNKSDEVICEIRP
---

## -description

An AVStream minidriver's IRP handler routine is called when these IRPs is dispatched by the device.

[IRP_MN_QUERY_REMOVE_DEVICE](/windows-hardware/drivers/kernel/irp-mn-query-remove-device)

[IRP_MN_QUERY_STOP_DEVICE](/windows-hardware/drivers/kernel/irp-mn-query-stop-device)

[IRP_MN_QUERY_INTERFACE](/windows-hardware/drivers/kernel/irp-mn-query-interface)

## -parameters

### -param Device [in]

Pointer to the [KSDEVICE](/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice) that dispatched the IRP.

### -param Irp [in]

The IRP issued by *Device*.

## -returns

Should return STATUS_SUCCESS or the error code that was returned from the attempt to perform the operation. If this is not the case, return an appropriate error code.

## -remarks

| IRP | Description |
|---|---|
| [IRP_MN_QUERY_REMOVE_DEVICE](/windows-hardware/drivers/kernel/irp-mn-query-remove-device) | The minidriver specifies this routine's address in the **QueryRemove** member of its [KSDEVICE_DISPATCH](/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice_dispatch) structure. This routine is called when an [IRP_MN_QUERY_REMOVE_DEVICE](/windows-hardware/drivers/kernel/irp-mn-query-remove-device) is dispatched by the device. It will usually be provided by minidrivers that want to prevent removal of the device or by minidrivers that must disallow activity that would otherwise prevent them from committing to a device removal operation. If this routine is not provided, AVStream will assume that the device can commit to a removal. The routine is called at IRQL = PASSIVE_LEVEL and may not return STATUS_PENDING; a success code indicates that the device can commit to a removal and an error code indicates that it cannot. Return success if the device can be removed (or drivers can be updated) without disrupting the machine. This routine is optional. |
| [IRP_MN_QUERY_STOP_DEVICE](/windows-hardware/drivers/kernel/irp-mn-query-stop-device) | The minidriver specifies a pointer to this routine in the **QueryStop** member of its [KSDEVICE_DISPATCH](/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice_dispatch) structure. Use *AVStrMiniQueryStop* to prevent the stopping of the device or to disallow activity that would prevent the minidriver from committing to a stop operation. If this routine is not specified, AVStream assumes that the minidriver can commit to a stop operation. This routine is optional. Success indicates that the device can commit to a stop and an error code indicates that it cannot. Do not return STATUS_PENDING. |
| [IRP_MN_QUERY_INTERFACE](/windows-hardware/drivers/kernel/irp-mn-query-interface) | A driver or system component sends this IRP to get information about an interface exported by your driver. For more information about the IRP, see [IRP_MN_QUERY_INTERFACE](/windows-hardware/drivers/kernel/irp-mn-query-interface). The minidriver specifies this routine's address in the **QueryInterface** member of its [KSDEVICE_DISPATCH](/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice_dispatch) structure. This routine is optional. |

## -see-also

[KSDEVICE](/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice)

[KSDEVICE_DISPATCH](/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice_dispatch)
