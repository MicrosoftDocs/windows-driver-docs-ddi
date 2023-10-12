---
UID: NC:mrx.PMRX_FINALIZE_SRVCALL_CALLDOWN
title: PMRX_FINALIZE_SRVCALL_CALLDOWN (mrx.h)
description: Learn more about the PMRX_FINALIZE_SRVCALL_CALLDOWN callback function.
tech.root: ifsk
ms.date: 10/11/2023
keywords: ["PMRX_FINALIZE_SRVCALL_CALLDOWN callback function"]
ms.keywords: MRxFinalizeSrvCall, MRxFinalizeSrvCall routine [Installable File System Drivers], PMRX_FINALIZE_SRVCALL_CALLDOWN, ifsk.mrxfinalizesrvcall, mrx/MRxFinalizeSrvCall, mrxref_7f2d4c59-1668-4c73-adc4-bdb6fac34d38.xml
req.header: mrx.h
req.include-header: Mrx.h
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
 - PMRX_FINALIZE_SRVCALL_CALLDOWN
 - mrx/PMRX_FINALIZE_SRVCALL_CALLDOWN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - mrx.h
api_name:
 - PMRX_FINALIZE_SRVCALL_CALLDOWN
---

# PMRX_FINALIZE_SRVCALL_CALLDOWN callback function

## -description

The **MRxFinalizeSrvCall** routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that a network mini-redirector finalize an SRV_CALL structure.

## -parameters

### -param SrvCall

[in, out] A pointer to the SRV_CALL structure to finalize.

### -param Force

[in] A pointer to a Boolean value that indicates if the disconnect is to be enforced immediately, ignoring the reference count on the SRV_CALL structure. The **Force** parameter is the **ForceFinalize** parameter passed to the [**RxFinalizeSrvCall**](../fcb/nf-fcb-rxfinalizesrvcall.md) routine. This action triggers a call to **MRxFinalizeSrvCall**.

## -returns

**MRxFinalizeSrvCall** returns STATUS_SUCCESS on success.

## -remarks

**MRxFinalizeSrvCall** is called when RDBSS is tearing down an SRV_CALL structure. The network mini-redirector is expected to close its connection to the server.

**MRxFinalizeSrvCall** is called by RDBSS after receiving an [**RxFinalizeSrvCall**](../fcb/nf-fcb-rxfinalizesrvcall.md) call. If [**RxFinalizeSrvCall**](../fcb/nf-fcb-rxfinalizenetroot.md) is called from a different process than the RDBSS system process, then the call to **MRxFinalizeSrvCall** is posted to a worker thread for later execution. At some later time **RxFinalizeSrvCall** is called to complete the finalization of the SRV_CALL structure.

RDBSS ignores the return value from the **MRxFinalizeSrvCall** call.

## -see-also

[**MRxCreateSrvCall**](nc-mrx-pmrx_create_srvcall.md)

[**MRxCreateVNetRoot**](nc-mrx-pmrx_create_v_net_root.md)

[**MRxExtractNetRootName**](nc-mrx-pmrx_extract_netroot_name.md)

[**MRxFinalizeNetRoot**](nc-mrx-pmrx_finalize_net_root_calldown.md)

[**MRxFinalizeVNetRoot**](nc-mrx-pmrx_finalize_v_net_root_calldown.md)

[**MRxPreparseName**](nc-mrx-pmrx_preparse_name.md)

[**MRxSrvCallWinnerNotify**](nc-mrx-pmrx_srvcall_winner_notify.md)

[**RxFinalizeSrvCall**](../fcb/nf-fcb-rxfinalizesrvcall.md)
