---
UID: NC:mrx.PMRX_FINALIZE_SRVCALL_CALLDOWN
title: PMRX_FINALIZE_SRVCALL_CALLDOWN
author: windows-driver-content
description: The MRxFinalizeSrvCall routine is called by RDBSS to request that a network mini-redirector finalize an SRV_CALL structure.
old-location: ifsk\mrxfinalizesrvcall.htm
old-project: ifsk
ms.assetid: f870334a-cf39-47a2-868a-f6fd7c3aee1c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: MRxFinalizeSrvCall, MRxFinalizeSrvCall routine [Installable File System Drivers], PMRX_FINALIZE_SRVCALL_CALLDOWN, ifsk.mrxfinalizesrvcall, mrx/MRxFinalizeSrvCall, mrxref_7f2d4c59-1668-4c73-adc4-bdb6fac34d38.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	mrx.h
api_name:
-	MRxFinalizeSrvCall
product: Windows
targetos: Windows
req.typenames: SetDSMCounters_IN, *PSetDSMCounters_IN
---

# PMRX_FINALIZE_SRVCALL_CALLDOWN callback


## -description


The <i>MRxFinalizeSrvCall</i> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector finalize an SRV_CALL structure. 


## -prototype


````
PMRX_FINALIZE_SRVCALL_CALLDOWN MRxFinalizeSrvCall;

NTSTATUS MRxFinalizeSrvCall(
  _Inout_ PMRX_SRV_CALL pSrvCall,
  _In_    BOOLEAN       Force
)
{ ... }
````


## -parameters




### -param SrvCall


### -param Force [in]

A pointer to a Boolean value that indicates if the disconnect is to be enforced immediately, ignoring the reference count on the SRV_CALL structure. The <i>Force</i> parameter is the <i>ForceFinalize</i> parameter passed to the <a href="..\fcb\nf-fcb-rxfinalizesrvcall.md">RxFinalizeSrvCall</a> routine. This action triggers a call to <i>MRxFinalizeSrvCall</i>.


#### - pSrvCall [in, out]

A pointer to the SRV_CALL structure to finalize. 


## -returns



<i>MRxFinalizeSrvCall</i> returns STATUS_SUCCESS on success. 




## -remarks



<i>MRxFinalizeSrvCall</i> is called when RDBSS is tearing down an SRV_CALL structure. The network mini-redirector is expected to close its connection to the server. 

<i>MRxFinalizeSrvCall</i> is called by RDBSS after receiving an <a href="..\fcb\nf-fcb-rxfinalizesrvcall.md">RxFinalizeSrvCall</a> call. If <a href="..\fcb\nf-fcb-rxfinalizenetroot.md">RxFinalizeNetRoot</a> is called from a different process than the RDBSS system process, then the call to <i>MRxFinalizeSrvCall</i> is posted to a worker thread for later execution. At some later time <b>RxFinalizeSrvCall</b> is called to complete the finalization of the SRV_CALL structure. 

RDBSS ignores the return value from the <i>MRxFinalizeSrvCall</i> call. 




## -see-also

<a href="..\mrx\nc-mrx-pmrx_preparse_name.md">MRxPreparseName</a>



<a href="..\mrx\nc-mrx-pmrx_finalize_v_net_root_calldown.md">MRxFinalizeVNetRoot</a>



<a href="..\mrx\nc-mrx-pmrx_create_srvcall.md">MRxCreateSrvCall</a>



<a href="..\mrx\nc-mrx-pmrx_srvcall_winner_notify.md">MRxSrvCallWinnerNotify</a>



<a href="..\fcb\nf-fcb-rxfinalizesrvcall.md">RxFinalizeSrvCall</a>



<a href="..\mrx\nc-mrx-pmrx_extract_netroot_name.md">MRxExtractNetRootName</a>



<a href="..\mrx\nc-mrx-pmrx_finalize_net_root_calldown.md">MRxFinalizeNetRoot</a>



<a href="..\mrx\nc-mrx-pmrx_create_v_net_root.md">MRxCreateVNetRoot</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PMRX_FINALIZE_SRVCALL_CALLDOWN routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

