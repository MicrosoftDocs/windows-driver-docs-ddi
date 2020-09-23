---
UID: NF:dispmprt.DlWaitForSingleObject
title: DlWaitForSingleObject function
description: Puts the current thread into a wait state until the given dispatch object is set to the signaled state, or (optionally) until the wait times out.
tech.root: display
ms.assetid: 658613b3-9f6f-40a4-86e1-27b61a5aadef
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["DlWaitForSingleObject function"]
ms.keywords: DlWaitForSingleObject
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
 - DlWaitForSingleObject
 - dispmprt/DlWaitForSingleObject
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - Displib.lib
 - Displib.dll
api_name:
 - DlWaitForSingleObject
product:
 - Windows
dev_langs:
 - c++
---

# DlWaitForSingleObject function


## -description

Puts the current thread into a wait state until the given dispatch object is set to the signaled state, or (optionally) until the wait times out.

## -parameters

### -param DeviceHandle

### -param pEvent

### -param Timeout

## -returns

This function returns VP_STATUS.

## -remarks

## -see-also

