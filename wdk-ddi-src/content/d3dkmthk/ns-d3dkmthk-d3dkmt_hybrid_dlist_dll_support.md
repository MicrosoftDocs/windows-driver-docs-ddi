---
UID: NS:d3dkmthk._D3DKMT_HYBRID_DLIST_DLL_SUPPORT
tech.root: display
title: D3DKMT_HYBRID_DLIST_DLL_SUPPORT
ms.date: 05/13/2021
targetos: Windows
description: The D3DKMT_HYBRID_DLIST_DLL_SUPPORT structure indicates whether the adapter provides dList DLL support on a hybrid system.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmthk.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3DKMT_HYBRID_DLIST_DLL_SUPPORT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_HYBRID_DLIST_DLL_SUPPORT
 - D3DKMT_HYBRID_DLIST_DLL_SUPPORT
f1_keywords:
 - _D3DKMT_HYBRID_DLIST_DLL_SUPPORT
 - d3dkmthk/_D3DKMT_HYBRID_DLIST_DLL_SUPPORT
 - D3DKMT_HYBRID_DLIST_DLL_SUPPORT
 - d3dkmthk/D3DKMT_HYBRID_DLIST_DLL_SUPPORT
dev_langs:
 - c++
---

## -description

The **D3DKMT_HYBRID_DLIST_DLL_SUPPORT** structure indicates whether the adapter provides [dList DLL support on a hybrid system](/windows-hardware/drivers/display/hybrid-system-ddi).

## -struct-fields

### -field Supported

If true, the adapter provides hybrid dList DLL support; otherwise, false.

## -remarks

For information on how to set up the DLL, see [Hybrid system DDI](/windows-hardware/drivers/display/hybrid-system-ddi).

For more general information on hybrid systems, see [Using cross-adapter resources in a hybrid system](/windows-hardware/drivers/display/using-cross-adapter-resources-in-a-hybrid-system).

## -see-also

[**KMTQUERYADAPTERINFOTYPE**](ne-d3dkmthk-_kmtqueryadapterinfotype.md)

[**Pfnd3dddiQuerydlistforapplication1**](../d3dumddi/nc-d3dumddi-pfnd3dddi_querydlistforapplication1.md)

[**Pfnd3dddiQuerydlistforapplication2**](../d3dumddi/nc-d3dumddi-pfnd3dddi_querydlistforapplication2.md)
