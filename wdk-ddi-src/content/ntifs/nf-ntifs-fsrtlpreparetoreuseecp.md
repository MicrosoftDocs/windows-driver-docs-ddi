---
UID: NF:ntifs.FsRtlPrepareToReuseEcp
title: FsRtlPrepareToReuseEcp function (ntifs.h)
description: The FsRtlPrepareToReuseEcp routine resets an extra create parameter (ECP) context structure, which prepares it for reuse.
old-location: ifsk\fsrtlpreparetoreuseecp.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlPrepareToReuseEcp function"]
ms.keywords: FsRtlPrepareToReuseEcp, FsRtlPrepareToReuseEcp routine [Installable File System Drivers], ifsk.fsrtlpreparetoreuseecp, ntifs/FsRtlPrepareToReuseEcp
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
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlPrepareToReuseEcp
 - ntifs/FsRtlPrepareToReuseEcp
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlPrepareToReuseEcp
---

# FsRtlPrepareToReuseEcp function


## -description

The <b>FsRtlPrepareToReuseEcp</b> routine resets an extra create parameter (ECP) context structure, which  prepares it for reuse.

## -parameters

### -param EcpContext 

[in]
A pointer to the ECP to prepare for reuse.

## -remarks

The <b>FsRtlPrepareToReuseEcp</b> allows reuse of an ECP used in a previous create request. This prevents having to initialize a new ECP with the same information.

The target of an ECP uses <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlacknowledgeecp">FsRtlAcknowledgeEcp</a> to mark the ECP as acknowledged. This indicates that the ECP was discovered and processed.  To reuse an previously acknowledged ECP, such as in processing a reparse, a driver can use <b>FsRtlPrepareToReuseEcp</b> to clear the acknowledged state from the ECP before sending it in another create request.

Within a file system minifilter driver, use <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltpreparetoreuseecp">FltPrepareToReuseEcp</a> to reuse an ECP.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff540148(v=vs.85)">ECP_LIST</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltpreparetoreuseecp">FltPrepareToReuseEcp</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlinsertextracreateparameter">FsRtlInsertExtraCreateParameter</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlisecpacknowledged">FsRtlIsEcpAcknowledged</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlremoveextracreateparameter">FsRtlRemoveExtraCreateParameter</a>
