---
UID: NF:wdm.PsAllocateAffinityToken
tech.root: kernel
title: PsAllocateAffinityToken
ms.date: 06/03/2021
targetos: Windows
description: The PsAllocateAffinityToken function allocates a thread affinity token.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - wdm.h
api_name:
 - PsAllocateAffinityToken
f1_keywords:
 - PsAllocateAffinityToken
 - wdm/PsAllocateAffinityToken
dev_langs:
 - c++
---

## -description

The **PsAllocateAffinityToken** function allocates a thread affinity token. After use, the token must be freed by calling [**PsFreeAffinityToken**](nf-wdm-psfreeaffinitytoken.md).

## -parameters

### -param AffinityToken [out]


Supplies a pointer to a buffer which, on success, receives a pointer to the newly allocated affinity token.

## -returns

Returns an NTSTATUS code.

## -remarks

## -see-also

[PsFreeAffinityToken](nf-wdm-psfreeaffinitytoken.md)
