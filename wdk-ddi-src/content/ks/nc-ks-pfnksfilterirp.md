---
UID: NC:ks.PFNKSFILTERIRP
title: PFNKSFILTERIRP (ks.h)
description: An AVStream minidriver's AVStrMiniFilterCreate routine is called when a filter receives an IRP.
tech.root: stream
ms.date: 03/06/2023
keywords: ["PFNKSFILTERIRP callback function"]
ms.keywords: AVStrMiniFilterClose, AVStrMiniFilterCreate, MyAVStrMiniFilterIRPHandler, MyAVStrMiniFilterIRPHandler routine [Streaming Media Devices], PFNKSFILTERIRP, avstclbk_76b73509-587e-47bd-9de7-92eac4237706.xml, ks/MyAVStrMiniFilterIRPHandler, stream.avstrminifiltercreate
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
 - PFNKSFILTERIRP
 - ks/PFNKSFILTERIRP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ks.h
api_name:
 - PFNKSFILTERIRP
---

## -description

An AVStream minidriver's *AVStrMiniFilterCreate* routine is called when a filter receives an IRP.

[IRP_MJ_CREATE](/windows-hardware/drivers/ifs/irp-mj-create)

[IRP_MJ_CLOSE](/windows-hardware/drivers/kernel/irp-mj-close)

## -parameters

### -param Filter [in]

Pointer to the [KSFILTER](/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter).

### -param Irp [in]

Pointer to the IRP for *Filter*.

## -returns

If the routine succeeds, return STATUS_SUCCESS or the error code.

## -remarks

| IRP | Description |
|---|---|
| [IRP_MJ_CREATE](/windows-hardware/drivers/ifs/irp-mj-create) | Typically, this routine is used by minidrivers that want to initialize the context and resources associated with the filter. The minidriver specifies this routine's address in the **Create** member of its [**KSFILTER_DISPATCH**](/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_dispatch) structure. At the point at which the routine is called, the file object has an associated context, and the KS object header has been allocated. This routine is called at IRQL = PASSIVE_LEVEL with the device mutex held. If the routine succeeds, the create operation is guaranteed to succeed. Return STATUS_SUCCESS or the error code that was returned from the attempt to create the filter. STATUS_PENDING is also a legal return code. If a minidriver returns STATUS_PENDING, AVStream will not complete the [IRP_MJ_CREATE](/windows-hardware/drivers/ifs/irp-mj-create) immediately. Before returning STATUS_PENDING, the minidriver must call [IoMarkIrpPending](/windows-hardware/drivers/ddi/wdm/nf-wdm-iomarkirppending). When the processing of the create is complete, the minidriver must set the IRP's status code and then call [KsCompletePendingRequest](/windows-hardware/drivers/ddi/ks/nf-ks-kscompletependingrequest). This routine is optional. |
| [IRP_MJ_CLOSE](/windows-hardware/drivers/kernel/irp-mj-close) | The minidriver specifies this routine's address in the **Close** member of its [**KSFILTER_DISPATCH**](/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_dispatch) structure. At the point at which the routine is called, any registered events on the filter have been freed, but the object is otherwise intact. This routine is called at IRQL = PASSIVE_LEVEL with the device mutex held. For more information about mutexes, see [Mutexes in AVStream](/windows-hardware/drivers/stream/mutexes-in-avstream). This routine is optional. Return STATUS_SUCCESS or STATUS_PENDING. If a minidriver returns STATUS_PENDING, AVStream will not complete the [IRP_MJ_CLOSE](/windows-hardware/drivers/kernel/irp-mj-close) immediately. Before returning STATUS_PENDING, however, the minidriver must call [IoMarkIrpPending](/windows-hardware/drivers/ddi/wdm/nf-wdm-iomarkirppending). Once the processing of the close is complete, the minidriver must set the IRP's status code and then call [KsCompletePendingRequest](/windows-hardware/drivers/ddi/ks/nf-ks-kscompletependingrequest). |

## -see-also

[IoMarkIrpPending](/windows-hardware/drivers/ddi/wdm/nf-wdm-iomarkirppending)

**[KSFILTER_DISPATCH](/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_dispatch)**
[KsCompletePendingRequest](/windows-hardware/drivers/ddi/ks/nf-ks-kscompletependingrequest)
