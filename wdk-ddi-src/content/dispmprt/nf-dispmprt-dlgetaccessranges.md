---
UID: NF:dispmprt.DlGetAccessRanges
title: DlGetAccessRanges function
author: windows-driver-content
description: Retrieves bus-relative configuration information and, if possible, claims these hardware resources in the registry for the caller.
tech.root: display
ms.assetid: c430c0a1-e9a2-49f8-b578-7cdd1c30cec4
ms.author: windowsdriverdev
ms.date: 04/04/2019 
ms.topic: function
f1_keywords:
 - "dispmprt/DlGetAccessRanges"
ms.keywords: DlGetAccessRanges
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
- DlGetAccessRanges
product: 
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# DlGetAccessRanges function


## -description

Retrieves bus-relative configuration information and, if possible, claims these hardware resources in the registry for the caller.

## -parameters

### -param DeviceHandle

A handle that represents a display adapter.

### -param NumRequestedResources

The number of requested resources.

### -param RequestedResources

The requested resources.

### -param NumAccessRanges

The number of access ranges.

### -param AccessRanges

The access ranges.

### -param VendorId

The vendor id.

### -param DeviceId

The device id.

### -param Slot

The memory slot.


## -returns

This function returns NTSTATUS.

## -remarks

## -see-also
