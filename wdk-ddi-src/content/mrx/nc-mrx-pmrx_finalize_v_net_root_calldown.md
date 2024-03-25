---
UID: NC:mrx.PMRX_FINALIZE_V_NET_ROOT_CALLDOWN
title: PMRX_FINALIZE_V_NET_ROOT_CALLDOWN (mrx.h)
description: Learn more about the PMRX_FINALIZE_V_NET_ROOT_CALLDOWN callback function.
tech.root: ifsk
ms.date: 10/11/2023
keywords: ["PMRX_FINALIZE_V_NET_ROOT_CALLDOWN callback function"]
ms.keywords: MRxFinalizeVNetRoot, MRxFinalizeVNetRoot routine [Installable File System Drivers], PMRX_FINALIZE_V_NET_ROOT_CALLDOWN, ifsk.mrxfinalizevnetroot, mrx/MRxFinalizeVNetRoot, mrxref_a5cc53ee-2d11-4987-aeb4-fe9cc2cc9b3e.xml
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
 - PMRX_FINALIZE_V_NET_ROOT_CALLDOWN
 - mrx/PMRX_FINALIZE_V_NET_ROOT_CALLDOWN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - mrx.h
api_name:
 - PMRX_FINALIZE_V_NET_ROOT_CALLDOWN
---

# PMRX_FINALIZE_V_NET_ROOT_CALLDOWN callback function

## -description

The **MRxFinalizeVNetRoot** routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that a network mini-redirector finalize a V_NET_ROOT structure.

## -parameters

### -param VirtualNetRoot

[in, out] A pointer to the V_NET_ROOT structure to finalize.

### -param Force

[in] A pointer to a Boolean value that indicates if the disconnect is to be forced. RDBSS currently passes **FALSE** for this parameter in all cases.

## -returns

**MRxFinalizeVNetRoot** returns STATUS_SUCCESS on success.

## -remarks

**MRxFinalizeVNetRoot** is called by RDBSS when it finalizes a NET_ROOT structure.

After the **MRxFinalizeVNetRoot** returns, RDBSS uninitializes the V_NET_ROOT structure members, dereferences the NET_ROOT structure, and releases the memory for the V_NET_ROOT structure.

RDBSS ignores the return value from **MRxFinalizeVNetRoot**.

## -see-also

[**MRxCreateSrvCall**](nc-mrx-pmrx_create_srvcall.md)

[**MRxCreateVNetRoot**](nc-mrx-pmrx_create_v_net_root.md)

[**MRxExtractNetRootName**](nc-mrx-pmrx_extract_netroot_name.md)

[**MRxFinalizeNetRoot**](nc-mrx-pmrx_finalize_net_root_calldown.md)

[**MRxPreparseName**](nc-mrx-pmrx_preparse_name.md)

[**MRxSrvCallWinnerNotify**](nc-mrx-pmrx_srvcall_winner_notify.md)

[**RxFinalizeSrvCall**](../fcb/nf-fcb-rxfinalizesrvcall.md)
