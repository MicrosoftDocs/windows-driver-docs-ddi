---
UID: NC:d3dkmthk.PFND3DKMT_BUDGETCHANGENOTIFICATIONCALLBACK
title: PFND3DKMT_BUDGETCHANGENOTIFICATIONCALLBACK (d3dkmthk.h)
description: The PFND3DKMT_BUDGETCHANGENOTIFICATIONCALLBACK callback function notifies of a budget change.
ms.date: 03/03/2022
keywords: ["PFND3DKMT_BUDGETCHANGENOTIFICATIONCALLBACK callback function"]
req.header: d3dkmthk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - PFND3DKMT_BUDGETCHANGENOTIFICATIONCALLBACK
 - d3dkmthk/PFND3DKMT_BUDGETCHANGENOTIFICATIONCALLBACK
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_BUDGETCHANGENOTIFICATIONCALLBACK
dev_langs:
 - c++
---

# PFND3DKMT_BUDGETCHANGENOTIFICATIONCALLBACK callback function

## -description

The **PFND3DKMT_BUDGETCHANGENOTIFICATIONCALLBACK** callback function notifies of a budget change.

## -parameters

### -param unnamedParam1

Pointer to a [D3DKMT_BUDGETCHANGENOTIFICATION](ns-d3dkmthk-_d3dkmt_budgetchangenotification.md) structure.

## -prototype

```cpp
//Declaration

PFND3DKMT_BUDGETCHANGENOTIFICATIONCALLBACK Pfnd3dkmtBudgetchangenotificationcallback; 

// Definition

VOID Pfnd3dkmtBudgetchangenotificationcallback 
(
  D3DKMT_BUDGETCHANGENOTIFICATION *
)
{...}

```
