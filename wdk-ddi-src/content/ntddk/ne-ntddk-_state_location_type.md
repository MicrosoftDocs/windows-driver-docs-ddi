---
UID: NE:ntddk._STATE_LOCATION_TYPE
title: _STATE_LOCATION_TYPE
author: windows-driver-content
description: 
ms.assetid: b1f859c2-ea58-4c37-9451-4521b83e3e8b
ms.author: windowsdriverdev
ms.date: 
ms.topic: enum
ms.keywords: _STATE_LOCATION_TYPE, STATE_LOCATION_TYPE, 
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: ntddk.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: STATE_LOCATION_TYPE
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	ntddk.h
apiname: 
-	_STATE_LOCATION_TYPE
product: Windows
targetos: Windows
---

# _STATE_LOCATION_TYPE enumeration

## -description

Defines values for persisted state locations for device and driver files. This enumeration is used by [**RtlGetPersistedStateLocation**](nf-ntddk-rtlgetpersistedstatelocation.md)

## -enum-fields

### -field LocationTypeRegistry
The device and driver files are stored in the registry.

### -field LocationTypeFileSystem
The device and driver files are stored in the file system.

### -field LocationTypeMaximum
Reserved.

## -remarks

## -see-also
[**RtlGetPersistedStateLocation**](nf-ntddk-rtlgetpersistedstatelocation.md)