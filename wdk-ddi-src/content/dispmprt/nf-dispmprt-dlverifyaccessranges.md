---
UID: NF:dispmprt.DlVerifyAccessRanges
title: DlVerifyAccessRanges function
author: windows-driver-content
description: Checks the registry for whether another driver has already claimed ownership of the specified bus-relative access ranges and any other hardware resources.
tech.root: display
ms.assetid: 72310495-2f98-4661-98d1-d55292f4e3ed
ms.author: windowsdriverdev
ms.date: 04/04/2019 
f1_keywords:
 - "dispmprt/DlVerifyAccessRanges"
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
topic_type: 
- apiref
api_type: 
- DllExport
api_location: 
- Displib.lib
- Displib.dll
api_name: 
- DlVerifyAccessRanges
product: 
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
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
