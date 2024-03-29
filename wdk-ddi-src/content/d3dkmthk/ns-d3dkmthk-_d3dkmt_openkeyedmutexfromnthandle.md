---
UID: NS:d3dkmthk._D3DKMT_OPENKEYEDMUTEXFROMNTHANDLE
title: _D3DKMT_OPENKEYEDMUTEXFROMNTHANDLE (d3dkmthk.h)
description: Contains information to open a keyed mutex from an NT handle to the process.
ms.date: 10/19/2018
keywords: ["D3DKMT_OPENKEYEDMUTEXFROMNTHANDLE structure"]
ms.keywords: _D3DKMT_OPENKEYEDMUTEXFROMNTHANDLE, D3DKMT_OPENKEYEDMUTEXFROMNTHANDLE,
req.header: d3dkmthk.h
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
req.typenames: D3DKMT_OPENKEYEDMUTEXFROMNTHANDLE
targetos: Windows
tech.root: display
f1_keywords:
 - _D3DKMT_OPENKEYEDMUTEXFROMNTHANDLE
 - d3dkmthk/_D3DKMT_OPENKEYEDMUTEXFROMNTHANDLE
 - D3DKMT_OPENKEYEDMUTEXFROMNTHANDLE
 - d3dkmthk/D3DKMT_OPENKEYEDMUTEXFROMNTHANDLE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_OPENKEYEDMUTEXFROMNTHANDLE
 - D3DKMT_OPENKEYEDMUTEXFROMNTHANDLE
---

# _D3DKMT_OPENKEYEDMUTEXFROMNTHANDLE structure


## -description

Contains information to open a keyed mutex from an NT handle to the process.

## -struct-fields

### -field hNtHandle

Handle to the process.

### -field hKeyedMutex

A handle to the keyed mutex in this process.

### -field pPrivateRuntimeData

A buffer that contains initial private data.

### -field PrivateRuntimeDataSize

The size, in bytes, of the buffer pointed to by the pPrivateRuntimeData member.

