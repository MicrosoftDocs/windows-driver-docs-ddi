---
UID: NF:dispmprt.DlSetBusData
title: DlSetBusData function
author: windows-driver-content
description: Sets bus-configuration data for an adapter on a dynamically configurable I/O bus with a published, standard interface.
tech.root: display
ms.assetid: 1c96d9b5-e074-41da-8867-a858d280fa10
ms.author: windowsdriverdev
ms.date: 04/04/2019 
f1_keywords:
 - "dispmprt/DlSetBusData"
ms.keywords: DlSetBusData
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
- DlSetBusData
product: 
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# DlSetBusData function


## -description

Sets bus-configuration data for an adapter on a dynamically configurable I/O bus with a published, standard interface.

## -parameters

### -param DeviceHandle

A handle that represents a display adapter.

### -param BusDataType

Specifies the type of bus data to be set.

### -param SlotNumber

For a *BusDataType* value that specifies the location of the device on the bus. This parameter should be zero for all other bus types.

### -param Buffer

Pointer to a caller-supplied storage area with configuration information specific to <i>BusDataType</i>.

### -param Offset

Specifies the byte offset within the PCI_COMMON_CONFIG structure at which the caller-supplied configuration values begin. A miniport driver can use PCI_COMMON_HDR_LENGTH to specify the offset of the device-specific area in PCI_COMMON_CONFIG.

### -param Length

Specifies the number of bytes in *Buffer*.


## -returns

This function returns ULONG.

## -remarks

## -see-also
