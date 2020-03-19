---
UID: NC:mrx.PMRX_FINALIZE_SRVCALL_CALLDOWN
title: PMRX_FINALIZE_SRVCALL_CALLDOWN (mrx.h)
description: The MRxFinalizeSrvCall routine is called by RDBSS to request that a network mini-redirector finalize an SRV_CALL structure.
old-location: ifsk\mrxfinalizesrvcall.htm
tech.root: ifsk
ms.assetid: f870334a-cf39-47a2-868a-f6fd7c3aee1c
ms.date: 04/16/2018
keywords: ["PMRX_FINALIZE_SRVCALL_CALLDOWN callback function"]
ms.keywords: MRxFinalizeSrvCall, MRxFinalizeSrvCall routine [Installable File System Drivers], PMRX_FINALIZE_SRVCALL_CALLDOWN, ifsk.mrxfinalizesrvcall, mrx/MRxFinalizeSrvCall, mrxref_7f2d4c59-1668-4c73-adc4-bdb6fac34d38.xml
f1_keywords:
 - "mrx/MRxFinalizeSrvCall"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- mrx.h
api_name:
- MRxFinalizeSrvCall
product:
- Windows
targetos: Windows
req.typenames: 
---

# PMRX_FINALIZE_SRVCALL_CALLDOWN callback function


## -description


The <i>MRxFinalizeSrvCall</i> routine is called by <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector finalize an SRV_CALL structure. 


## -parameters




### -param SrvCall


### -param Force [in]

A pointer to a Boolean value that indicates if the disconnect is to be enforced immediately, ignoring the reference count on the SRV_CALL structure. The <i>Force</i> parameter is the <i>ForceFinalize</i> parameter passed to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizesrvcall">RxFinalizeSrvCall</a> routine. This action triggers a call to <i>MRxFinalizeSrvCall</i>.


#### - pSrvCall [in, out]

A pointer to the SRV_CALL structure to finalize. 


## -returns



<i>MRxFinalizeSrvCall</i> returns STATUS_SUCCESS on success. 




## -remarks



<i>MRxFinalizeSrvCall</i> is called when RDBSS is tearing down an SRV_CALL structure. The network mini-redirector is expected to close its connection to the server. 

<i>MRxFinalizeSrvCall</i> is called by RDBSS after receiving an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizesrvcall">RxFinalizeSrvCall</a> call. If <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizenetroot">RxFinalizeNetRoot</a> is called from a different process than the RDBSS system process, then the call to <i>MRxFinalizeSrvCall</i> is posted to a worker thread for later execution. At some later time <b>RxFinalizeSrvCall</b> is called to complete the finalization of the SRV_CALL structure. 

RDBSS ignores the return value from the <i>MRxFinalizeSrvCall</i> call. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_create_srvcall">MRxCreateSrvCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_create_v_net_root">MRxCreateVNetRoot</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_extract_netroot_name">MRxExtractNetRootName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_finalize_net_root_calldown">MRxFinalizeNetRoot</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_finalize_v_net_root_calldown">MRxFinalizeVNetRoot</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_preparse_name">MRxPreparseName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_srvcall_winner_notify">MRxSrvCallWinnerNotify</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizesrvcall">RxFinalizeSrvCall</a>
 

 

