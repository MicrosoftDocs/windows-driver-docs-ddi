---
UID: NS:d3dkmddi._DXGKARG_QUERYCONNECTIONCHANGE
title: _DXGKARG_QUERYCONNECTIONCHANGE (d3dkmddi.h)
description: Used to hold the arguments for DXGKDDI_QUERYCONNECTIONCHANGE.
old-location: display\dxgkarg_queryconnectionchange.htm
ms.date: 05/10/2018
keywords: ["DXGKARG_QUERYCONNECTIONCHANGE structure"]
ms.keywords: "*IN_PDXGKARG_QUERYCONNECTIONCHANGE, DXGKARG_QUERYCONNECTIONCHANGE, DXGKARG_QUERYCONNECTIONCHANGE structure [Display Devices], _DXGKARG_QUERYCONNECTIONCHANGE, d3dkmddi/DXGKARG_QUERYCONNECTIONCHANGE, display.dxgkarg_queryconnectionchange"
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
req.typenames: DXGKARG_QUERYCONNECTIONCHANGE
f1_keywords:
 - _DXGKARG_QUERYCONNECTIONCHANGE
 - d3dkmddi/_DXGKARG_QUERYCONNECTIONCHANGE
 - DXGKARG_QUERYCONNECTIONCHANGE
 - d3dkmddi/DXGKARG_QUERYCONNECTIONCHANGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKARG_QUERYCONNECTIONCHANGE
---

# _DXGKARG_QUERYCONNECTIONCHANGE structure


## -description

Used to hold the arguments for <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryconnectionchange">DXGKDDI_QUERYCONNECTIONCHANGE</a>.

## -struct-fields

### -field ConnectionChange

[out] Buffer into which the oldest available change is copied by driver.
