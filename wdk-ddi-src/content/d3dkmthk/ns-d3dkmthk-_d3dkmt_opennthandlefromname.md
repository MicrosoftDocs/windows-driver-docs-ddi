---
UID: NS:d3dkmthk._D3DKMT_OPENNTHANDLEFROMNAME
title: _D3DKMT_OPENNTHANDLEFROMNAME (d3dkmthk.h)
description: Describes information that is required to open an NT handle to the process from a graphics adapter name.
old-location: display\d3dkmt_opennthandlefromname.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_OPENNTHANDLEFROMNAME structure"]
ms.keywords: D3DKMT_OPENNTHANDLEFROMNAME, D3DKMT_OPENNTHANDLEFROMNAME structure [Display Devices], _D3DKMT_OPENNTHANDLEFROMNAME, d3dkmthk/D3DKMT_OPENNTHANDLEFROMNAME, display.d3dkmt_opennthandlefromname
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.typenames: D3DKMT_OPENNTHANDLEFROMNAME
f1_keywords:
 - _D3DKMT_OPENNTHANDLEFROMNAME
 - d3dkmthk/_D3DKMT_OPENNTHANDLEFROMNAME
 - D3DKMT_OPENNTHANDLEFROMNAME
 - d3dkmthk/D3DKMT_OPENNTHANDLEFROMNAME
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmthk.h
api_name:
 - _D3DKMT_OPENNTHANDLEFROMNAME
 - D3DKMT_OPENNTHANDLEFROMNAME
---

# _D3DKMT_OPENNTHANDLEFROMNAME structure


## -description

Describes information that is required to open an NT handle to the process from a graphics adapter name.

## -struct-fields

### -field dwDesiredAccess [in]

Specifies read and write access for the resource.

### -field pObjAttrib [in]

A pointer to an <a href="/windows/win32/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a> structure that specifies attributes of the adapter, including its name.

### -field hNtHandle [out]

An NT handle to the process.

