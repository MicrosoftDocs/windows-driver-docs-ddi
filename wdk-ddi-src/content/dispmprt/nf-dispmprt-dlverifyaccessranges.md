---
UID: NF:dispmprt.DlVerifyAccessRanges
title: DlVerifyAccessRanges function
description: Checks the registry for whether another driver has already claimed ownership of the specified bus-relative access ranges and any other hardware resources.
tech.root: display
ms.date: 04/04/2019
keywords: ["DlVerifyAccessRanges function"]
ms.keywords: DlVerifyAccessRanges
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
 - DlVerifyAccessRanges
 - dispmprt/DlVerifyAccessRanges
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - Displib.lib
 - Displib.dll
api_name:
 - DlVerifyAccessRanges
dev_langs:
 - c++
---

# DlVerifyAccessRanges function


## -description

Checks the registry for whether another driver has already claimed ownership of the specified bus-relative access ranges and any other hardware resources.

## -parameters

### -param DeviceHandle

### -param NumAccessRanges

### -param AccessRanges

## -returns

This function returns VP_STATUS.

## -remarks

## -see-also

