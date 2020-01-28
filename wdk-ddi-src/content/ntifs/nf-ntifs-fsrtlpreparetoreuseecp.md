---
UID: NF:ntifs.FsRtlPrepareToReuseEcp
title: FsRtlPrepareToReuseEcp function (ntifs.h)
description: The FsRtlPrepareToReuseEcp routine resets an extra create parameter (ECP) context structure, which prepares it for reuse.
old-location: ifsk\fsrtlpreparetoreuseecp.htm
tech.root: ifsk
ms.assetid: 88967BD6-C633-40D0-BE4F-2B08494EA5B0
ms.date: 04/16/2018
ms.keywords: FsRtlPrepareToReuseEcp, FsRtlPrepareToReuseEcp routine [Installable File System Drivers], ifsk.fsrtlpreparetoreuseecp, ntifs/FsRtlPrepareToReuseEcp
f1_keywords:
 - "ntifs/FsRtlPrepareToReuseEcp"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlPrepareToReuseEcp
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlPrepareToReuseEcp function


## -description


The <b>FsRtlPrepareToReuseEcp</b> routine resets an extra create parameter (ECP) context structure, which  prepares it for reuse.


## -parameters




### -param EcpContext [in]

A pointer to the ECP to prepare for reuse.


## -remarks



The <b>FsRtlPrepareToReuseEcp</b> allows reuse of an ECP used in a previous create request. This prevents having to initialize a new ECP with the same information.

The target of an ECP uses <a href="https://msdn.microsoft.com/library/windows/hardware/ff545574">FsRtlAcknowledgeEcp</a> to mark the ECP as acknowledged. This indicates that the ECP was discovered and processed.  To reuse an previously acknowledged ECP, such as in processing a reparse, a driver can use <b>FsRtlPrepareToReuseEcp</b> to clear the acknowledged state from the ECP before sending it in another create request.

Within a file system minifilter driver, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltpreparetoreuseecp">FltPrepareToReuseEcp</a> to reuse an ECP.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff540148(v=vs.85)">ECP_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltpreparetoreuseecp">FltPrepareToReuseEcp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546179">FsRtlInsertExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546808">FsRtlIsEcpAcknowledged</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547203">FsRtlRemoveExtraCreateParameter</a>
 

 

