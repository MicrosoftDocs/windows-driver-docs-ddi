---
UID: NS:ntddk._DEBUG_TRANSPORT_DATA
title: _DEBUG_TRANSPORT_DATA
author: windows-driver-content
description: Describes debug-transport specific data for use by the transport.
ms.assetid: 6a091719-3ec5-41e4-be56-b93112daef19
ms.date: 09/30/2018
ms.topic: struct
ms.keywords: _DEBUG_TRANSPORT_DATA, DEBUG_TRANSPORT_DATA, *PDEBUG_TRANSPORT_DATA, 
req.header: ntddk.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DEBUG_TRANSPORT_DATA, *PDEBUG_TRANSPORT_DATA
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ntddk.h
api_name: 
-	_DEBUG_TRANSPORT_DATA
product: Windows
targetos: Windows
ms.custom: RS5
---

# _DEBUG_TRANSPORT_DATA structure

## -description
Describes debug-transport specific data for use by the transport.

## -struct-fields

### -field HwContextSize
The hardware context size.
 
### -field UseSerialFraming
Indicates whether this device is using serial framing.

### -field ValidUSBCoreId
Indicates whether the USB kernel debug controller is needed.
 
### -field USBCoreId
The USB core ID to use.

## -remarks

## -see-also
