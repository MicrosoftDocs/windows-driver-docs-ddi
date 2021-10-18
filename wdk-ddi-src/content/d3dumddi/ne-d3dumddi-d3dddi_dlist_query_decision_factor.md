---
UID: NE:d3dumddi._D3DDDI_DLIST_QUERY_DECISION_FACTOR
tech.root: display
title: D3DDDI_DLIST_QUERY_DECISION_FACTOR
ms.date: 05/13/2021
targetos: Windows
description: A D3DDDI_DLIST_QUERY_DECISION_FACTOR enum value describes the factor that determined the GPU preference returned by pfnQueryDlistForApplication2Cb.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3dumddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _D3DDDI_DLIST_QUERY_DECISION_FACTOR
 - D3DDDI_DLIST_QUERY_DECISION_FACTOR
f1_keywords:
 - _D3DDDI_DLIST_QUERY_DECISION_FACTOR
 - d3dumddi/_D3DDDI_DLIST_QUERY_DECISION_FACTOR
 - D3DDDI_DLIST_QUERY_DECISION_FACTOR
 - d3dumddi/D3DDDI_DLIST_QUERY_DECISION_FACTOR
dev_langs:
 - c++
---

## -description

A **D3DDDI_DLIST_QUERY_DECISION_FACTOR** enum value describes the factor that determined the GPU preference returned by [**pfnQueryDlistForApplication2Cb**](nc-d3dumddi-pfnd3dddi_querydlistforapplication2.md).

## -enum-fields

### -field D3DDDI_DLIST_QUERY_DECISION_FACTOR_UNDEFINED

The factor is unknown or not represented by the available enum values.

### -field D3DDDI_DLIST_QUERY_DECISION_FACTOR_DLIST_APP_ENTRY

GPU preference was determined by dList app entry.

### -field D3DDDI_DLIST_QUERY_DECISION_FACTOR_APP_SPECIFIED_BY_USER

GPU preference was determined by user-specified preference for this specific app.

### -field D3DDDI_DLIST_QUERY_DECISION_FACTOR_GLOBAL_PREFERENCE_BY_USER

GPU preference was determined by user-specified global preference.

## -remarks

The **D3DDDI_DLIST_QUERY_DECISION_FACTOR** value returned by [**pfnQueryDlistForApplication2Cb**](nc-d3dumddi-pfnd3dddi_querydlistforapplication2.md) has no impact on runtime application behavior.

## -see-also

[**D3DDDI_DLIST_QUERY_RESULT**](ne-d3dumddi-d3dddi_dlist_query_result.md)

[**pfnQueryDlistForApplication2Cb**](nc-d3dumddi-pfnd3dddi_querydlistforapplication2.md)
