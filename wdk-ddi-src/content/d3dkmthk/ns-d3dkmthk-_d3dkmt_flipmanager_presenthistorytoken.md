---
UID: NS:d3dkmthk._D3DKMT_FLIPMANAGER_PRESENTHISTORYTOKEN
title: D3DKMT_FLIPMANAGER_PRESENTHISTORYTOKEN (d3dkmthk.h)
description: Identifies a flip present-history token.
ms.date: 04/10/2024
keywords: ["D3DKMT_FLIPMANAGER_PRESENTHISTORYTOKEN structure"]
req.header: d3dkmthk.h
req.construct-type: structure
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3DKMT_FLIPMANAGER_PRESENTHISTORYTOKEN
targetos: Windows
tech.root: display
f1_keywords:
 - _D3DKMT_FLIPMANAGER_PRESENTHISTORYTOKEN
 - d3dkmthk/_D3DKMT_FLIPMANAGER_PRESENTHISTORYTOKEN
 - D3DKMT_FLIPMANAGER_PRESENTHISTORYTOKEN
 - d3dkmthk/D3DKMT_FLIPMANAGER_PRESENTHISTORYTOKEN
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_FLIPMANAGER_PRESENTHISTORYTOKEN
 - D3DKMT_FLIPMANAGER_PRESENTHISTORYTOKEN
---

# D3DKMT_FLIPMANAGER_PRESENTHISTORYTOKEN structure (d3dkmthk.h)



## -description

The **D3DKMT_FLIPMANAGER_PRESENTHISTORYTOKEN** structure identifies a flip present-history token.

## -struct-fields

### -field hPrivateData

Handle to the token's private data.

### -field PresentAtQpc

Present the frame at this QPC (Query Performance Counter) time.

### -field Flags

Attributes of a flip present-history token.

### -field Flags.Discard

Discard the token.

### -field Flags.PresentAt

Present the token.

### -field Flags.hPrivateDataIsPointer

The handle to the private data (**hPrivateData**) is a pointer.

### -field Flags.Reserved

This member is reserved.

### -field Flags.Value

An alternative way to access the flags.
