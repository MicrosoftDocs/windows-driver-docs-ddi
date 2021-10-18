---
UID: NC:d3dumddi.PFND3DDDI_QUERYDLISTFORAPPLICATION2
tech.root: display
title: PFND3DDDI_QUERYDLISTFORAPPLICATION2
ms.date: 05/13/2021
targetos: Windows
description: The pfnQueryDlistForApplication2Cb callback function queries a dList for an application.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dumddi.h
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
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_QUERYDLISTFORAPPLICATION2
f1_keywords:
 - PFND3DDDI_QUERYDLISTFORAPPLICATION2
 - d3dumddi/PFND3DDDI_QUERYDLISTFORAPPLICATION2
dev_langs:
 - c++
---

## -description

The **pfnQueryDlistForApplication2Cb** callback function queries the dList for an application.

## -parameters

### -param unnamedParam1

[out] Pointer to a [**D3DDDI_DLIST_QUERY_RESULT**](ne-d3dumddi-d3dddi_dlist_query_result.md) value that describes the returned GPU preference for the queried application.

### -param unnamedParam2

[out] Pointer to a [**D3DDDI_DLIST_QUERY_DECISION_FACTOR**](ne-d3dumddi-d3dddi_dlist_query_decision_factor.md) value that describes the factor that determined the returned GPU preference.

### -param unnamedParam3

[in] A handle to the graphics adapter object. This handle is passed to the [**pfnEscapeCb**](nc-d3dumddi-pfnd3dddi_escapecb.md) callback function pointed to by *unnamedParam4*.

### -param unnamedParam4

[in] Pointer to a [**pfnEscapeCb**](nc-d3dumddi-pfnd3dddi_escapecb.md) callback function that shares info with the display miniport driver.

## -returns

Returns **S_OK**, or an appropriate error result if the operation is not successful.

## -remarks

Starting with WDDM 2.9, drivers must support **pfnQueryDlistForApplication2Cb** instead of [**pfnQueryDlistForApplication1Cb**](nc-d3dumddi-pfnd3dddi_querydlistforapplication1.md).

The **pfnQueryDlistForApplication2Cb** callback function is called by the user-mode graphics runtime (DXGI) during Microsoft Direct3D initialization on a hybrid system to determine which GPU an application should run on. A *dList* is a list of applications that need cross-adapter shared surfaces for high-performance rendering on the discrete GPU.

The [**D3DDDI_DLIST_QUERY_RESULT**](ne-d3dumddi-d3dddi_dlist_query_result.md) and [**D3DDDI_DLIST_QUERY_DECISION_FACTOR**](ne-d3dumddi-d3dddi_dlist_query_decision_factor.md) returned in this DDI help the runtime to ensure and improve the quality of DxDb content updates, by assessing for risk of application regressions for an update.

Hybrid system drivers need to [set up and register a dList DLL](/windows-hardware/drivers/display/hybrid-system-ddi) that exports this function. For more information on hybrid systems, see [Using cross-adapter resources in a hybrid system](/windows-hardware/drivers/display/using-cross-adapter-resources-in-a-hybrid-system).

## -see-also

[**D3DDDI_DLIST_QUERY_DECISION_FACTOR**](ne-d3dumddi-d3dddi_dlist_query_decision_factor.md)

[**D3DDDI_DLIST_QUERY_RESULT**](ne-d3dumddi-d3dddi_dlist_query_result.md)

[**pfnEscapeCb**](nc-d3dumddi-pfnd3dddi_escapecb.md)
