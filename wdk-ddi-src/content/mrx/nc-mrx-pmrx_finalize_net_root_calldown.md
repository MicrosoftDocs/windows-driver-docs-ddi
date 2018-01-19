---
UID: NC:mrx.PMRX_FINALIZE_NET_ROOT_CALLDOWN
title: PMRX_FINALIZE_NET_ROOT_CALLDOWN
author: windows-driver-content
description: The MRxFinalizeNetRoot routine is called by RDBSS to request that a network mini-redirector finalize a NET_ROOT structure.
old-location: ifsk\mrxfinalizenetroot.htm
old-project: ifsk
ms.assetid: 59f5b6e0-9edc-45c9-9d22-1555edb8f7c6
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _SetDSMCounters_IN, SetDSMCounters_IN, *PSetDSMCounters_IN
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
req.alt-api: MRxFinalizeNetRoot
req.alt-loc: mrx.h
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
req.typenames: SetDSMCounters_IN, *PSetDSMCounters_IN
---

# PMRX_FINALIZE_NET_ROOT_CALLDOWN callback



## -description
The<i> MRxFinalizeNetRoot</i> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector finalize a NET_ROOT structure.



## -prototype

````
PMRX_FINALIZE_NET_ROOT_CALLDOWN MRxFinalizeNetRoot;

NTSTATUS MRxFinalizeNetRoot(
  _Inout_ PMRX_NET_ROOT pNetRoot,
  _In_    PBOOLEAN      ForceDisconnect
)
{ ... }
````


## -parameters

### -param pNetRoot [in, out]

A pointer to the NET_ROOT structure to finalize. 


### -param ForceDisconnect [in]

A pointer to a Boolean value that indicates if the disconnect is to be forced. RDBSS currently passes <b>FALSE</b> for this parameter in all cases.


## -returns
<i>MRxFinalizeNetRoot</i> returns STATUS_SUCCESS on success. 


## -remarks
<i>MRxFinalizeNetRoot</i> is called by RDBSS when RDBSS finalizes a NET_ROOT structure. Because a NET_ROOT structure is always associated with one or more V_NET_ROOT structures, this finalization normally occurs when the last V_NET_ROOT structure on the NET_ROOT structure is finalized. 

RDBSS ignores the return value from <i>MRxFinalizeNetRoot</i>. 


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549864">MRxCreateSrvCall</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549869">MRxCreateVNetRoot</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550649">MRxExtractNetRootName</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550656">MRxFinalizeSrvCall</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550663">MRxFinalizeVNetRoot</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550750">MRxPreparseName</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550824">MRxSrvCallWinnerNotify</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20MRxFinalizeNetRoot routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

