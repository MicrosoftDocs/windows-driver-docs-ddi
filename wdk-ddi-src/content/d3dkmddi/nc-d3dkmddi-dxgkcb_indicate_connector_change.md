---
UID: NC:d3dkmddi.DXGKCB_INDICATE_CONNECTOR_CHANGE
title: DXGKCB_INDICATE_CONNECTOR_CHANGE (d3dkmddi.h)
description: DXGKCB_INDICATE_CONNECTOR_CHANGE is called by the KMD to indicate that it has added changes to its change queue which the OS should now query.
old-location: display\dxgkcb_indicate_connector_change.htm
ms.assetid: D3C76DC0-7A6B-4E1E-8277-F6410D4B474B
ms.date: 05/10/2018
keywords: ["DXGKCB_INDICATE_CONNECTOR_CHANGE callback function"]
ms.keywords: DXGKCB_INDICATE_CONNECTOR_CHANGE, DXGKCB_INDICATE_CONNECTOR_CHANGE callback, DXGKCB_INDICATE_CONNECTOR_CHANGE callback function [Display Devices], d3dkmddi/DXGKCB_INDICATE_CONNECTOR_CHANGE, display.dxgkcb_indicate_connector_change
req.header: d3dkmddi.h
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
req.irql: DISPATCH_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKCB_INDICATE_CONNECTOR_CHANGE
 - d3dkmddi/DXGKCB_INDICATE_CONNECTOR_CHANGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_INDICATE_CONNECTOR_CHANGE
product:
 - Windows
---

# DXGKCB_INDICATE_CONNECTOR_CHANGE callback function


## -description

DXGKCB_INDICATE_CONNECTOR_CHANGE is called by the KMD to indicate that it has added changes to its change queue which the OS should now query.

## -parameters

### -param hAdapter

A handle that identifies the adapter.

## -returns

If this routine succeeds, it returns STATUS_SUCCESS.

