---
UID: NF:dispmprt.DlFreeDeviceBase
title: DlFreeDeviceBase function
author: windows-driver-content
description: Frees a range of bus-relative device I/O ports or memory addresses previously mapped into the system address space.
tech.root: display
ms.assetid: b5c33cfe-bdc7-49a5-a090-ae3472a681a7
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["DlFreeDeviceBase function"]
ms.keywords: DlFreeDeviceBase
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
 - DlFreeDeviceBase
 - dispmprt/DlFreeDeviceBase
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - Displib.lib
 - Displib.dll
api_name:
 - DlFreeDeviceBase
product:
 - Windows
dev_langs:
 - c++
---

# DlFreeDeviceBase function


## -description

Frees a range of bus-relative device I/O ports or memory addresses previously mapped into the system address space.

## -parameters

### -param DeviceHandle

A handle that represents a display adapter.

### -param MappedAddress

Specifies the base address of the mapped range to be freed.

## -remarks

## -see-also

