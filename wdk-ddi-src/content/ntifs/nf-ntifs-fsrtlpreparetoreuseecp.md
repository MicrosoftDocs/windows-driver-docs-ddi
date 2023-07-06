---
UID: NF:ntifs.FsRtlPrepareToReuseEcp
title: FsRtlPrepareToReuseEcp function (ntifs.h)
description: Learn more about the FsRtlPrepareToReuseEcp routine.
tech.root: ifsk
ms.date: 07/06/2023
keywords: ["FsRtlPrepareToReuseEcp function"]
ms.keywords: FsRtlPrepareToReuseEcp, ifsk.fsrtlpreparetoreuseecp, ntifs/FsRtlPrepareToReuseEcp
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
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

The **FsRtlPrepareToReuseEcp** routine resets an extra create parameter (ECP) context structure, which  prepares it for reuse.

## -parameters

### -param EcpContext [in]

A pointer to the ECP to prepare for reuse.

## -remarks

The **FsRtlPrepareToReuseEcp** allows reuse of an ECP used in a previous create request. This prevents having to initialize a new ECP with the same information.

The target of an ECP uses [**FsRtlAcknowledgeEcp**](nf-ntifs-fsrtlacknowledgeecp.md) to mark the ECP as acknowledged. This indicates that the ECP was discovered and processed.  To reuse an previously acknowledged ECP, such as in processing a reparse, a driver can use **FsRtlPrepareToReuseEcp** to clear the acknowledged state from the ECP before sending it in another create request.

Within a file system minifilter driver, use [**FltPrepareToReuseEcp**](../fltkernel/nf-fltkernel-fltpreparetoreuseecp.md) to reuse an ECP.

## -see-also

[**ECP_LIST**](/windows-hardware/drivers/ifs/introduction-to-extra-create-parameters)

[**FltPrepareToReuseEcp**](../fltkernel/nf-fltkernel-fltpreparetoreuseecp.md)

[**FsRtlInsertExtraCreateParameter**](nf-ntifs-fsrtlinsertextracreateparameter.md)

[**FltIsEcpAcknowledged**](../fltkernel/nf-fltkernel-fltisecpacknowledged.md)

[**FsRtlRemoveExtraCreateParameter**](nf-ntifs-fsrtlremoveextracreateparameter.md)
