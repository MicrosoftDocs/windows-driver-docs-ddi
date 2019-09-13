---
UID: NC:d3dkmddi.DXGKDDI_UPDATEHWCONTEXTSTATE
title: DXGKDDI_UPDATEHWCONTEXTSTATE (d3dkmddi.h)
description: Used to update the hardware context state.
old-location: display\dxgkddi_updatehwcontextstate.htm
ms.assetid: 1187A302-CD7D-418E-B48F-74D1FF29C991
ms.date: 05/10/2018
ms.keywords: DXGKDDI_UPDATEHWCONTEXTSTATE, DXGKDDI_UPDATEHWCONTEXTSTATE callback, DXGKDDI_UPDATEHWCONTEXTSTATE callback function [Display Devices], d3dkmddi/DXGKDDI_UPDATEHWCONTEXTSTATE, display.dxgkddi_updatehwcontextstate
ms.topic: callback
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
req.irql: requires_(PASSIVE_LEVEL)
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3dkmddi/DXGKDDI_UPDATEHWCONTEXTSTATE"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_UPDATEHWCONTEXTSTATE
product:
 - Windows
---

# DXGKDDI_UPDATEHWCONTEXTSTATE callback function

## -description

Used to update the hardware context state.

## -parameters

### -param hAdapter

A handle to the generated adapter.

### -param pUpdateHwContextState

A pointer used by the function to update the hardware context state.

## -returns

Returns STATUS_SUCCESS if completed successfully.

