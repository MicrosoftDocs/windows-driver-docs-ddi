---
UID: NF:wdm.PsRevertToUserMultipleGroupAffinityThread
tech.root: kernel
title: PsRevertToUserMultipleGroupAffinityThread
ms.date: 06/03/2021
targetos: Windows
description: The PsRevertToUserMultipleGroupAffinityThread function reverts the current thread to its previous affinity as indicated by the given affinity token.
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
 - PsRevertToUserMultipleGroupAffinityThread
f1_keywords:
 - PsRevertToUserMultipleGroupAffinityThread
 - wdm/PsRevertToUserMultipleGroupAffinityThread
dev_langs:
 - c++
---

## -description

The **PsRevertToUserMultipleGroupAffinityThread** function reverts the current thread to its previous affinity as indicated by the given affinity token.

The given affinity token must have been filled in by a successful call to [**PsSetSystemMultipleGroupAffinityThread**](nf-wdm-pssetsystemmultiplegroupaffinitythread.md).

## -parameters

### -param AffinityToken

[in]
Supplies a pointer to an affinity token.

## -remarks

## -see-also

[PsSetSystemMultipleGroupAffinityThread](nf-wdm-pssetsystemmultiplegroupaffinitythread.md).
