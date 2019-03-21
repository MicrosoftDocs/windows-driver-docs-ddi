---
UID: NF:dispmprt.DlGetDeviceBase
title: DlGetDeviceBase function
author: windows-driver-content
description: Maps a range of bus-relative device memory or I/O addresses into system space.
tech.root: display
ms.assetid: 5d64fca7-23ed-4bf0-9a81-fdbced013728
ms.author: windowsdriverdev
ms.date: 04/04/2019 
ms.topic: function
ms.keywords: DlGetDeviceBase
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
- DlGetDeviceBase
product: 
- Windows
targetos: Windows

---

# DlGetDeviceBase function


## -description

Maps a range of bus-relative device memory or I/O addresses into system space.

## -parameters

### -param DeviceHandle

A handle that represents a display adapter.

### -param IoAddress



### -param NumberOfUchars



### -param InIoSpace




## -returns

This function returns PVOID.

## -remarks

## -see-also