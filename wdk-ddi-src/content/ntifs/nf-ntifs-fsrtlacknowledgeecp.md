---
UID: NF:ntifs.FsRtlAcknowledgeEcp
title: FsRtlAcknowledgeEcp function (ntifs.h)
description: Learn more about the FsRtlAcknowledgeEcp routine.
tech.root: ifsk
ms.date: 07/06/2023
keywords: ["FsRtlAcknowledgeEcp function"]
ms.keywords: FsRtlAcknowledgeEcp, ifsk.fsrtlacknowledgeecp, ntifs/FsRtlAcknowledgeEcp
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows Vista
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
 - FsRtlAcknowledgeEcp
 - ntifs/FsRtlAcknowledgeEcp
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlAcknowledgeEcp
---

# FsRtlAcknowledgeEcp function

## -description

The **FsRtlAcknowledgeEcp** routine marks an extra create parameter (ECP) context structure as acknowledged.

## -parameters

### -param EcpContext [in]

A pointer to the ECP to mark as acknowledged.

## -remarks

When **FsRtlAcknowledgeEcp** marks an ECP as acknowledged, it could indicate   whether the ECP has been looked at, used, processed, or any other condition of the ECP.  

You can use the [**FltIsEcpAcknowledged**](../fltkernel/nf-fltkernel-fltisecpacknowledged.md) routine to determine if a particular ECP has been marked as acknowledged.

## -see-also

[**ECP_LIST**](/windows-hardware/drivers/ifs/introduction-to-extra-create-parameters)

[**FltAllocateExtraCreateParameterFromLookasideList**](../fltkernel/nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md)

[**FltFreeExtraCreateParameter**](../fltkernel/nf-fltkernel-fltfreeextracreateparameter.md)

[**FltGetEcpListFromCallbackData**](../fltkernel/nf-fltkernel-fltgetecplistfromcallbackdata.md)

[**FltIsEcpAcknowledged**](../fltkernel/nf-fltkernel-fltisecpacknowledged.md)

[**FltIsEcpFromUserMode**](../fltkernel/nf-fltkernel-fltisecpfromusermode.md)

[**FltRemoveExtraCreateParameter**](../fltkernel/nf-fltkernel-fltremoveextracreateparameter.md)

[**FltSetEcpListIntoCallbackData**](../fltkernel/nf-fltkernel-fltsetecplistintocallbackdata.md)
