---
UID: NF:dispmprt.DlScanRom
title: DlScanRom function
author: windows-driver-content
description: Performs a case-sensitive search for a specified string in ROM.
tech.root: display
ms.assetid: 62e855f9-d066-44b6-a104-eec2c079b315
ms.author: windowsdriverdev
ms.date: 04/04/2019 
ms.topic: function
ms.keywords: DlScanRom
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
- DlScanRom
product: 
- Windows
targetos: Windows

ms.custom: 19H1
---

# DlScanRom function


## -description

Performs a case-sensitive search for a specified string in ROM.

## -parameters

### -param DeviceHandle

A handle that represents a display adapter.

### -param RomBase

Specifies the base ROM address at which the search should start.

### -param RomLength

Specifies the size in bytes of the mapped ROM to be searched.

### -param String

Pointer to the driver-allocated string to search for.


## -returns

This function returns BOOLEAN.

## -remarks

## -see-also
