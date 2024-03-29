---
UID: NS:d3dkmddi._DXGKARG_CREATEPROTECTEDSESSION
title: _DXGKARG_CREATEPROTECTEDSESSION (d3dkmddi.h)
description: The DXGKARG_CREATEPROTECTEDSESSION structure contains data that is used to create a protected session.
old-location: display\dxgkarg_createprotectedsession.htm
ms.date: 05/10/2018
keywords: ["DXGKARG_CREATEPROTECTEDSESSION structure"]
ms.keywords: "*INOUT_PDXGKARG_CREATEPROTECTEDSESSION, DXGKARG_CREATEPROTECTEDSESSION, DXGKARG_CREATEPROTECTEDSESSION structure [Display Devices], _DXGKARG_CREATEPROTECTEDSESSION, d3dkmddi/DXGKARG_CREATEPROTECTEDSESSION, display.dxgkarg_createprotectedsession"
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
req.typenames: DXGKARG_CREATEPROTECTEDSESSION
f1_keywords:
 - _DXGKARG_CREATEPROTECTEDSESSION
 - d3dkmddi/_DXGKARG_CREATEPROTECTEDSESSION
 - DXGKARG_CREATEPROTECTEDSESSION
 - d3dkmddi/DXGKARG_CREATEPROTECTEDSESSION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_CREATEPROTECTEDSESSION
 - DXGKARG_CREATEPROTECTEDSESSION
---

# _DXGKARG_CREATEPROTECTEDSESSION structure


## -description

Used to create a protected session.

## -struct-fields

### -field hProtectedSession

An assigned value for the protected session that was passed to DxgkDdiCreateProtectedSession.

### -field pPrivateDriverData

A pointer to the driver data.

### -field PrivateDriverDataSize

The size of the data.

