---
UID: NC:dispmprt.PBANKED_SECTION_ROUTINE
title: PBANKED_SECTION_ROUTINE
description: Graphics support routine.
tech.root: display
ms.assetid: f2d3b495-2977-4b51-a613-0e04e2e94c53
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["PBANKED_SECTION_ROUTINE callback function"]
req.header: dispmprt.h
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
ms.custom: 19H1
f1_keywords:
 - PBANKED_SECTION_ROUTINE
 - dispmprt/PBANKED_SECTION_ROUTINE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - PBANKED_SECTION_ROUTINE
product:
 - Windows
dev_langs:
 - c++
---

# PBANKED_SECTION_ROUTINE callback function


## -description

Graphics support routine.

## -parameters

### -param ReadBank

### -param WriteBank

### -param Context 

## -prototype

```
//Declaration

PBANKED_SECTION_ROUTINE PbankedSectionRoutine; 

// Definition

VOID PbankedSectionRoutine 
(
	ULONG ReadBank
	ULONG WriteBank
	PVOID Context
)
{...}

```

## -remarks

## -see-also

