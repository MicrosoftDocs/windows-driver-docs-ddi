---
UID: NS:d3dkmthk._D3DKMT_ADAPTER_VERIFIER_VIDMM_FLAGS
title: _D3DKMT_ADAPTER_VERIFIER_VIDMM_FLAGS (d3dkmthk.h)
description: The display adapter verifier video memory management flags.
ms.date: 03/08/2022
keywords: ["D3DKMT_ADAPTER_VERIFIER_VIDMM_FLAGS structure"]
ms.keywords: _D3DKMT_ADAPTER_VERIFIER_VIDMM_FLAGS, D3DKMT_ADAPTER_VERIFIER_VIDMM_FLAGS,
req.header: d3dkmthk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3DKMT_ADAPTER_VERIFIER_VIDMM_FLAGS
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _D3DKMT_ADAPTER_VERIFIER_VIDMM_FLAGS
 - d3dkmthk/_D3DKMT_ADAPTER_VERIFIER_VIDMM_FLAGS
 - D3DKMT_ADAPTER_VERIFIER_VIDMM_FLAGS
 - d3dkmthk/D3DKMT_ADAPTER_VERIFIER_VIDMM_FLAGS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_ADAPTER_VERIFIER_VIDMM_FLAGS
 - D3DKMT_ADAPTER_VERIFIER_VIDMM_FLAGS
dev_langs:
 - c++
---

# _D3DKMT_ADAPTER_VERIFIER_VIDMM_FLAGS structure

## -description

The display adapter verifier video memory management flags.

## -struct-fields

### -field AlwaysRepatch

Always repatch.

### -field FailSharedPrimary

Fail shared primary.

### -field FailProbeAndLock

Fail probe and lock.

### -field AlwaysDiscardOffer

Always discard offer.

### -field NeverDiscardOffer

Never discard offer.

### -field ForceComplexLock

Force complex lock.

### -field NeverPrepatch

Never prepatch.

### -field ExpectPreparationFailure

Expect preparation failure.

### -field TakeSplitPoint

Take split point.

### -field FailAcquireSwizzlingRange

Fail acquire swizzling range.

### -field PagingPathLockSubrange

Paging path lock subrange.

### -field PagingPathLockMinrange

Paging path lock min-range.

### -field FailVaRotation

Fail VA rotation.

### -field NoDemotion

No demotion.

### -field FailDefragPass

Fail defragmentation pass.

### -field AlwaysProcessOfferList

Always process offer list.

### -field AlwaysDecommitOffer

Always decommit offer.

### -field NeverMoveDefrag

Never move defragmentation.

### -field AlwaysRelocateDisplayableResources

Always relocate displayable resources.

### -field AlwaysFailGrowVPRMoves

Always fail grow VPR moves.

### -field Reserved

Reserved for internal use.

### -field Value

The value used to operate over the other members.

## -remarks

## -see-also

[D3DKMT_ADAPTER_VERIFIER_OPTION_DATA](ns-d3dkmthk-_d3dkmt_adapter_verifier_option_data.md)
