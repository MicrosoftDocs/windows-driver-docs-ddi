---
UID: NC:ks.PFNKSPINIRP
title: PFNKSPINIRP (ks.h)
description: An AVStream minidriver's routine is called when an activity on the pin is performed and it receives these IRPs:IRP_MJ_CREATEIRP_MJ_CLOSE
tech.root: stream
ms.date: 03/06/2023
keywords: ["PFNKSPINIRP callback function"]
ms.keywords: AVStrMiniPinCreate, AVStrMiniPinCreate routine [Streaming Media Devices], PFNKSPINIRP, avstclbk_0feeeb85-88fe-43d7-83e4-399b0c26aa53.xml, ks/AVStrMiniPinCreate, stream.avstrminipincreate
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
 - PFNKSPINIRP
 - ks/PFNKSPINIRP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ks.h
api_name:
 - PFNKSPINIRP
---

## -description

An AVStream minidriver's routine is called when an activity on the pin is performed and it receives these IRPs:

- [IRP_MJ_CREATE](/windows-hardware/drivers/ifs/irp-mj-create)

- [IRP_MJ_CLOSE](/windows-hardware/drivers/kernel/irp-mj-close)

## -parameters

### -param Pin [in]

Pointer to the [KSPIN](./ns-ks-_kspin.md) that was just created.

### -param Irp [in]

Pointer to the  IRP for *Pin*.

## -returns

If the routine succeeds, the operation is guaranteed to succeed. Return STATUS_SUCCESS or STATUS_PENDING.

## -remarks

| IRP | Description |
|---|---|
| [IRP_MJ_CREATE](/windows-hardware/drivers/ifs/irp-mj-create) | Typically, this routine is used by minidrivers that want to initialize the context and resources associated with the pin. The minidriver specifies this routine's address in the **Create** member of its [**KSPIN_DISPATCH**](./ns-ks-_kspin_dispatch.md) structure. This routine is called when a pin is created. At the point at which this routine is called, the file object has an associated context, and the KS object header has been allocated. Typically, this function will be provided by minidrivers that want to initialize the context and resources associated with the pin. The filter control mutex is held while in this function. The function will be called at IRQL = PASSIVE_LEVEL. This routine is optional. If the routine succeeds, the create operation is guaranteed to succeed. Return STATUS_SUCCESS or STATUS_PENDING. If a minidriver returns STATUS_PENDING, AVStream will not complete the [IRP_MJ_CREATE](/windows-hardware/drivers/ifs/irp-mj-create) immediately. Before returning STATUS_PENDING, however, the minidriver must call [IoMarkIrpPending](../wdm/nf-wdm-iomarkirppending.md). Once the processing of the create is complete, the minidriver must set the IRP's status code and then call [KsCompletePendingRequest](./nf-ks-kscompletependingrequest.md). |
| [IRP_MJ_CLOSE](/windows-hardware/drivers/kernel/irp-mj-close) | The minidriver specifies this routine's address in the **Close** member of its [**KSPIN_DISPATCH**](./ns-ks-_kspin_dispatch.md) structure. At the point at which the routine is called, any registered events on the pin have been freed, but the object is otherwise intact. The filter control mutex is held while in this function. For more information about mutexes, please see [Mutexes in AVStream](/windows-hardware/drivers/stream/mutexes-in-avstream). This routine is optional. |

## -see-also

[IoMarkIrpPending](../wdm/nf-wdm-iomarkirppending.md)

[KSPIN_DISPATCH](./ns-ks-_kspin_dispatch.md)

[KsCompletePendingRequest](./nf-ks-kscompletependingrequest.md)