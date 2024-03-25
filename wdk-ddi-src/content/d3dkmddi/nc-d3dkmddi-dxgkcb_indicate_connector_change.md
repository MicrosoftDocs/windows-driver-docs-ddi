---
UID: NC:d3dkmddi.DXGKCB_INDICATE_CONNECTOR_CHANGE
title: DXGKCB_INDICATE_CONNECTOR_CHANGE (d3dkmddi.h)
description: DXGKCB_INDICATE_CONNECTOR_CHANGE is called by the KMD to indicate that it has added changes to its change queue which the OS should now query.
old-location: display\dxgkcb_indicate_connector_change.htm
ms.date: 10/13/2021
keywords: ["DXGKCB_INDICATE_CONNECTOR_CHANGE callback function"]
ms.keywords: DXGKCB_INDICATE_CONNECTOR_CHANGE, DXGKCB_INDICATE_CONNECTOR_CHANGE callback, DXGKCB_INDICATE_CONNECTOR_CHANGE callback function [Display Devices], d3dkmddi/DXGKCB_INDICATE_CONNECTOR_CHANGE, display.dxgkcb_indicate_connector_change
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703 (WDDM 2.2)
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
---

# DXGKCB_INDICATE_CONNECTOR_CHANGE callback function

## -description

A kernel-mode display miniport driver calls **DXGKCB_INDICATE_CONNECTOR_CHANGE** to indicate that it has added changes to its change queue which the OS should now query.

## -parameters

### -param hAdapter [in]

Handle that identifies the adapter.

## -returns

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, returns an appropriate NTSTATUS error code.

## -remarks

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, call **DxgkCbIndicateConnectorChange** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

## -see-also

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
