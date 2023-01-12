---
UID: NC:winsplp.ROUTER_NOTIFY_CALLBACK
title: ROUTER_NOTIFY_CALLBACK (winsplp.h)
description: Describes the ROUTER_NOTIFY_CALLBACK callback function.
tech.root: print
ms.date: 07/27/2022
keywords: ["ROUTER_NOTIFY_CALLBACK callback function"]
ms.keywords: ROUTER_NOTIFY_CALLBACK, ROUTER_NOTIFY_CALLBACK callback, ROUTER_NOTIFY_CALLBACK callback function [Print Devices], print.router_notify_callback, winsplp/ROUTER_NOTIFY_CALLBACK
req.header: winsplp.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - ROUTER_NOTIFY_CALLBACK
 - winsplp/ROUTER_NOTIFY_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Winsplp.h
api_name:
 - ROUTER_NOTIFY_CALLBACK
---

## -description

Describes the **ROUTER_NOTIFY_CALLBACK** callback function.

## -parameters

### -param dwCommand [in]

Defines the **DWORD** parameter *dwCommand*.

### -param pContext [in]

Defines the **PVOID** parameter *pContext*.

### -param dwColor [in]

Defines the **DWORD** parameter *dwColor*.

### -param pNofityInfo [in]

Defines the **PPRINTER_NOTIFY_INFO** parameter *pNofityInfo*.

### -param fdwFlags [in]

Defines the **DWORD** parameter *fdwFlags*.

### -param pdwResult [out]

Defines the **PDWORD** parameter *pdwResult*.

## -returns

Returns a **BOOL** value.
