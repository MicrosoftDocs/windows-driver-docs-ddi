---
UID: NE:wwan._WWAN_CONTEXT_OPERATIONS
title: _WWAN_CONTEXT_OPERATIONS
author: windows-driver-content
description: The WWAN_CONTEXT_OPERATIONS enumeration specifies the types of operation used in a Set request for a provisioned context in a mobile broadband (MBB) modem.
ms.assetid: 30c43b14-55c8-4f24-855d-23a3e017ad01
ms.author: windowsdriverdev
ms.date: 08/22/2018
ms.topic: enum
ms.keywords: _WWAN_CONTEXT_OPERATIONS, WWAN_CONTEXT_OPERATIONS, *PWWAN_CONTEXT_OPERATIONS, 
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: wwan.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: WWAN_CONTEXT_OPERATIONS, *PWWAN_CONTEXT_OPERATIONS
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	wwan.h
api_name: 
-	_WWAN_CONTEXT_OPERATIONS
product: 
- Windows
targetos: Windows
---

# _WWAN_CONTEXT_OPERATIONS enumeration

## -description

The **WWAN_CONTEXT_OPERATIONS** enumeration specifies the types of operation used in a Set request for a provisioned context in a mobile broadband (MBB) modem.

## -enum-fields

### -field WwanContextOperationDefault 

The default operation for overwriting an existing context in the modem. 

### -field WwanContextOperationDelete 

Delete the context.

### -field WwanContextOperationRestoreFactory 

Restore factory preconfigured contexts for the Provider ID of the currently inserted SIM.

### -field WwanContextOperationMaximum 

The maximum value for this enumeration.

## -remarks

This enumeration is used in the [**WWAN_SET_CONTEXT_V2**](ns-wwan-_wwan_set_context_v2.md) structure.

## -see-also

[**WWAN_SET_CONTEXT_V2**](ns-wwan-_wwan_set_context_v2.md)