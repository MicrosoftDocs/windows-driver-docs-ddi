---
UID: NC:mrx.PMRX_FINALIZE_NET_ROOT_CALLDOWN
title: PMRX_FINALIZE_NET_ROOT_CALLDOWN
description: The MRxFinalizeNetRoot routine is called by RDBSS to request that a network mini-redirector finalize a NET_ROOT structure.
old-location: ifsk\mrxfinalizenetroot.htm
tech.root: ifsk
ms.assetid: 59f5b6e0-9edc-45c9-9d22-1555edb8f7c6
ms.date: 04/16/2018
ms.keywords: MRxFinalizeNetRoot, MRxFinalizeNetRoot routine [Installable File System Drivers], PMRX_FINALIZE_NET_ROOT_CALLDOWN, ifsk.mrxfinalizenetroot, mrx/MRxFinalizeNetRoot, mrxref_5f5d7468-3257-4800-99fe-e5e6b7c99e37.xml
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
-	MRxFinalizeNetRoot
product:
- Windows
targetos: Windows
req.typenames: 
---

# PMRX_FINALIZE_NET_ROOT_CALLDOWN callback function


## -description


The<i> MRxFinalizeNetRoot</i> routine is called by <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector finalize a NET_ROOT structure.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549864">MRxCreateSrvCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549869">MRxCreateVNetRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550649">MRxExtractNetRootName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550656">MRxFinalizeSrvCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550663">MRxFinalizeVNetRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550750">MRxPreparseName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550824">MRxSrvCallWinnerNotify</a>
 

 

