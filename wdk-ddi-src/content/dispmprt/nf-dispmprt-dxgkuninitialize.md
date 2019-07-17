---
UID: NF:dispmprt.DxgkUnInitialize
title: DxgkUnInitialize function
author: windows-driver-content
description: Unloads the DirectX graphics kernel subsystem (Dxgkrnl.sys).
tech.root: display
ms.assetid: 5cbff717-75d4-46bc-9b0b-b02a1da7a601
ms.author: windowsdriverdev
ms.date: 04/04/2019 
ms.topic: function
f1_keywords:
 - "dispmprt/DxgkUnInitialize"
ms.keywords: DxgkUnInitialize
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
- DxgkUnInitialize
product: 
- Windows
targetos: Windows

ms.custom: 19H1
---

# DxgkUnInitialize function


## -description

Unloads the DirectX graphics kernel subsystem (Dxgkrnl.sys).

## -parameters

### -param DriverObject

A pointer to a [DRIVER_OBJECT](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_driver_object) structure.


## -returns

This function returns NTSTATUS.

## -remarks

## -see-also
