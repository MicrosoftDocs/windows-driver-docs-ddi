---
UID: NF:wdm.PsFreeAffinityToken
tech.root: kernel
title: PsFreeAffinityToken
ms.date: 06/03/2021
targetos: Windows
description: The PsFreeAffinityToken function frees an affinity token that was allocated by PsAllocateAffinityToken.
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
req.target-min-winverclnt: 
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
 - PsFreeAffinityToken
f1_keywords:
 - PsFreeAffinityToken
 - wdm/PsFreeAffinityToken
dev_langs:
 - c++
---

## -description

The **PsFreeAffinityToken** function frees an affinity token that was allocated by [**PsAllocateAffinityToken**](nf-wdm-psallocateaffinitytoken.md).

## -parameters

### -param AffinityToken

Supplies a pointer to an affinity token.

## -remarks

## -see-also

[PsAllocateAffinityToken](nf-wdm-psallocateaffinitytoken.md)
