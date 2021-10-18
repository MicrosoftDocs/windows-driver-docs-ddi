---
UID: NE:d3dumddi._D3DDDI_DLIST_QUERY_RESULT
tech.root: display
title: D3DDDI_DLIST_QUERY_RESULT
ms.date: 05/13/2021
targetos: Windows
description: A D3DDDI_DLIST_QUERY_RESULT enum value describes the GPU preference returned by pfnQueryDlistForApplication2Cb for the queried application.
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
 - _D3DDDI_DLIST_QUERY_RESULT
 - D3DDDI_DLIST_QUERY_RESULT
f1_keywords:
 - _D3DDDI_DLIST_QUERY_RESULT
 - d3dumddi/_D3DDDI_DLIST_QUERY_RESULT
 - D3DDDI_DLIST_QUERY_RESULT
 - d3dumddi/D3DDDI_DLIST_QUERY_RESULT
dev_langs:
 - c++
---

## -description

A **D3DDDI_DLIST_QUERY_RESULT** enum value describes the GPU preference returned by [**pfnQueryDlistForApplication2Cb**](nc-d3dumddi-pfnd3dddi_querydlistforapplication2.md) for the queried application.

## -enum-fields

### -field D3DDDI_DLIST_QUERY_RESULT_NO_DATA

There is no GPU preference for this app.

### -field D3DDDI_DLIST_QUERY_RESULT_POWER_SAVING_PREFERENCE

The preference is to run this app on the power saving (also known as the default) GPU.

### -field D3DDDI_DLIST_QUERY_RESULT_HIGH_PERFORMANCE_PREFERENCE

The preference is to run this app on the high performance GPU.

## -see-also

[**D3DDDI_DLIST_QUERY_DECISION_FACTOR**](ne-d3dumddi-d3dddi_dlist_query_decision_factor.md)

[**pfnQueryDlistForApplication2Cb**](nc-d3dumddi-pfnd3dddi_querydlistforapplication2.md)
