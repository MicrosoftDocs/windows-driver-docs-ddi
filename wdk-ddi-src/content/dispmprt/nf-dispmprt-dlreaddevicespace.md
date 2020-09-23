---
UID: NF:dispmprt.DlReadDeviceSpace
title: DlReadDeviceSpace function
description: Reads from a device configuration space or the expansion ROM of a display adapter.
tech.root: display
ms.assetid: 57b1447a-e923-47b8-a17d-c9668be70e26
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["DlReadDeviceSpace function"]
ms.keywords: DlReadDeviceSpace
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
 - DlReadDeviceSpace
 - dispmprt/DlReadDeviceSpace
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - Displib.lib
 - Displib.dll
api_name:
 - DlReadDeviceSpace
product:
 - Windows
dev_langs:
 - c++
---

# DlReadDeviceSpace function


## -description

Reads from a device configuration space or the expansion ROM of a display adapter.

## -parameters

### -param DeviceHandle

A handle that represents a display adapter.

### -param DataType

The type of read transaction to be performed.

### -param SlotNumber

### -param Buffer

A pointer to a caller-allocated buffer that receives the data read from the configuration space or ROM.

### -param Offset

The offset, into the configuration space or the expansion ROM, at which the read transaction begins.

### -param Length

The number of bytes to be read.

## -returns

This function returns ULONG.

## -remarks

## -see-also

