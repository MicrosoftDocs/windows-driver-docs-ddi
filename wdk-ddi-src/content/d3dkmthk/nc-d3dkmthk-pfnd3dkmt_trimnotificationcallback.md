---
UID: NC:d3dkmthk.PFND3DKMT_TRIMNOTIFICATIONCALLBACK
title: PFND3DKMT_TRIMNOTIFICATIONCALLBACK (d3dkmthk.h)
description: Trim notification.
ms.date: 03/04/2022
keywords: ["PFND3DKMT_TRIMNOTIFICATIONCALLBACK callback function"]
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
 - PFND3DKMT_TRIMNOTIFICATIONCALLBACK
 - d3dkmthk/PFND3DKMT_TRIMNOTIFICATIONCALLBACK
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_TRIMNOTIFICATIONCALLBACK
dev_langs:
 - c++
---

# PFND3DKMT_TRIMNOTIFICATIONCALLBACK callback function

## -description

Trim notification.

## -syntax

```cpp
PFND3DKMT_TRIMNOTIFICATIONCALLBACK PfnD3dkmtTrimNotificationCallback;

void Pfnd3dkmtTrimnotificationcallback(
    D3DKMT_TRIMNOTIFICATION *unnamedParam1
)
{...}
```

## -parameters

### -param unnamedParam1

Pointer to a [D3DKMT_TRIMNOTIFICATION](ns-d3dkmthk-_d3dkmt_trimnotification.md) structure.

## -remarks

## -see-also
