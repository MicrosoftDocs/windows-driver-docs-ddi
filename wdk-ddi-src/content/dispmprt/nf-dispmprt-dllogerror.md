---
UID: NF:dispmprt.DlLogError
title: DlLogError function
author: windows-driver-content
description: Logs errors to the system event log when a miniport driver detects a hardware error condition during I/O operations.
tech.root: display
ms.assetid: b440bac9-d91a-48d6-ac7a-695341fe589e
ms.author: windowsdriverdev
ms.date: 04/04/2019 
ms.topic: function
f1_keywords:
 - "dispmprt/DlLogError"
ms.keywords: DlLogError
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
- DlLogError
product: 
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# DlLogError function


## -description

Logs errors to the system event log when a miniport driver detects a hardware error condition during I/O operations.

## -parameters

### -param DeviceHandle

A handle that represents a display adapter.

### -param Vrp



### -param ErrorCode

Specifies a miniport driver-defined error code that indicates the type of hardware error.

### -param UniqueId

Specifies a unique identifier for the error.

## -remarks

## -see-also
