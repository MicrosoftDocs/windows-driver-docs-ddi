---
UID: NC:d3dkmddi.DXGKDDI_DISPLAYDETECTCONTROL
title: DXGKDDI_DISPLAYDETECTCONTROL (d3dkmddi.h)
description: Used to turn hot plug detection on and off and to initiate status polls on either a specific target or all targets.
old-location: display\dxgkddi_displaydetectcontrol.htm
ms.assetid: 6F10EA4D-BCDE-475E-9937-414CB83F6F2F
ms.date: 05/10/2018
keywords: ["DXGKDDI_DISPLAYDETECTCONTROL callback function"]
ms.keywords: DXGKDDI_DISPLAYDETECTCONTROL, DXGKDDI_DISPLAYDETECTCONTROL callback, DXGKDDI_DISPLAYDETECTCONTROL callback function [Display Devices], d3dkmddi/DXGKDDI_DISPLAYDETECTCONTROL, display.dxgkddi_displaydetectcontrol
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
 - "d3dkmddi/DXGKDDI_DISPLAYDETECTCONTROL"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_DISPLAYDETECTCONTROL
product:
 - Windows
---

# DXGKDDI_DISPLAYDETECTCONTROL callback function

## -description

Used to turn hot plug detection on and off and to initiate status polls on either a specific target or all targets.

## -parameters

### -param hAdapter

A handle that identifies the adapter.

### -param pDisplayDetectControl

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_displaydetectcontrol">DXGKARG_DISPLAYDETECTCONTROL</a> structure that describes the detection action which is requested.

## -returns

If this routine succeeds, it returns STATUS_SUCCESS.

## -remarks

This function is always called at PASSIVE level so the supporting code should be made pageable.

The status returned only reflects the call, not the status of connectors. If the driver detects a change, it will respond by calling DxgkCbIndicateConnectorChange.  If a poll of one or more targets was requested, the driver should return once the request has been submitted to hardware, rather than waiting for the poll to complete.

DXGK_DDCT_POLLONE applies only to the specified target id while DXGK_DDCT_POLLALL applies to all targets.  It would be an OS error to request either of these types of detection control if HPD is not enabled so the driver can simply fail the call with STATUS_INVALID_PARAMETER.

