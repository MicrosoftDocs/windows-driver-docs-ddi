---
UID: NC:mrx.PMRX_FINALIZE_NET_ROOT_CALLDOWN
title: PMRX_FINALIZE_NET_ROOT_CALLDOWN (mrx.h)
description: The MRxFinalizeNetRoot routine is called by RDBSS to request that a network mini-redirector finalize a NET_ROOT structure.
old-location: ifsk\mrxfinalizenetroot.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["PMRX_FINALIZE_NET_ROOT_CALLDOWN callback function"]
ms.keywords: MRxFinalizeNetRoot, MRxFinalizeNetRoot routine [Installable File System Drivers], PMRX_FINALIZE_NET_ROOT_CALLDOWN, ifsk.mrxfinalizenetroot, mrx/MRxFinalizeNetRoot, mrxref_5f5d7468-3257-4800-99fe-e5e6b7c99e37.xml
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
 - PMRX_FINALIZE_NET_ROOT_CALLDOWN
 - mrx/PMRX_FINALIZE_NET_ROOT_CALLDOWN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - mrx.h
api_name:
 - PMRX_FINALIZE_NET_ROOT_CALLDOWN
---

# PMRX_FINALIZE_NET_ROOT_CALLDOWN callback function


## -description

The<i> MRxFinalizeNetRoot</i> routine is called by <a href="/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector finalize a NET_ROOT structure.

## -parameters

### -param NetRoot

### -param Force

#### - ForceDisconnect [in]

A pointer to a Boolean value that indicates if the disconnect is to be forced. RDBSS currently passes <b>FALSE</b> for this parameter in all cases.


#### - pNetRoot [in, out]

A pointer to the NET_ROOT structure to finalize.

## -returns

<i>MRxFinalizeNetRoot</i> returns STATUS_SUCCESS on success.

## -remarks

<i>MRxFinalizeNetRoot</i> is called by RDBSS when RDBSS finalizes a NET_ROOT structure. Because a NET_ROOT structure is always associated with one or more V_NET_ROOT structures, this finalization normally occurs when the last V_NET_ROOT structure on the NET_ROOT structure is finalized. 

RDBSS ignores the return value from <i>MRxFinalizeNetRoot</i>.

## -see-also

<a href="/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_create_srvcall">MRxCreateSrvCall</a>



<a href="/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_create_v_net_root">MRxCreateVNetRoot</a>



<a href="/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_extract_netroot_name">MRxExtractNetRootName</a>



<a href="/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_finalize_srvcall_calldown">MRxFinalizeSrvCall</a>



<a href="/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_finalize_v_net_root_calldown">MRxFinalizeVNetRoot</a>



<a href="/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_preparse_name">MRxPreparseName</a>



<a href="/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_srvcall_winner_notify">MRxSrvCallWinnerNotify</a>

