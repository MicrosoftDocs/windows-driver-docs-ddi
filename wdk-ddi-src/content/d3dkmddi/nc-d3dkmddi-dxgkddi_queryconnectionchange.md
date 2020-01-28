---
UID: NC:d3dkmddi.DXGKDDI_QUERYCONNECTIONCHANGE
title: DXGKDDI_QUERYCONNECTIONCHANGE (d3dkmddi.h)
description: The OS calls this in response to a status change reported through DxgkCbIndicateConnectorChange or when the OutputFlags.ConnectorStatusChanges field indicates that a call to SetTimingsFromVidPn has detected connector status changes.
old-location: display\dxgkddi_queryconnectionchange.htm
ms.assetid: 8C09B692-3439-4ACD-942D-F7A107E2B4DA
ms.date: 04/16/2018
ms.keywords: DXGKDDI_QUERYCONNECTIONCHANGE, DXGKDDI_QUERYCONNECTIONCHANGE callback, DXGKDDI_QUERYCONNECTIONCHANGE callback function [Display Devices], d3dkmddi/DXGKDDI_QUERYCONNECTIONCHANGE, display.dxgkddi_queryconnectionchange
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
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3dkmddi/DXGKDDI_QUERYCONNECTIONCHANGE"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_QUERYCONNECTIONCHANGE
product:
 - Windows
---

# DXGKDDI_QUERYCONNECTIONCHANGE callback function

## -description

The OS calls this in response to a status change reported through [DxgkCbIndicateConnectorChange](nc-d3dkmddi-dxgkcb_indicate_connector_change.md) or when the OutputFlags.ConnectorStatusChanges field indicates that a call to [SetTimingsFromVidPn](nc-d3dkmddi-dxgkddi_settimingsfromvidpn.md) has detected connector status changes.

## -parameters

### -param hAdapter

A handle that identifies the adapter.

### -param pQueryConnectionChange

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryconnectionchange">DXGKARG_QUERYCONNECTIONCHANGE</a> structure that provides the OS allocated buffer into which the oldest change should be copied by the driver. The oldest change is judged by lowest ConnectionChangeId.

## -returns

|Return value|Description|
|--- |--- |
|STATUS_SUCCESS|Returned if the routine succeeds and returns the requested change.|
|STATUS_ALREADY_COMPLETE|Returned if the routine succeeds, but the changes have already been reported to the OS.|

## -remarks

This function is always called at PASSIVE level so the supporting code should be made pageable.

