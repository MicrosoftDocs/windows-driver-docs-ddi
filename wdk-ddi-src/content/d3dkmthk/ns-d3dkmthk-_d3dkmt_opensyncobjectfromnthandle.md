---
UID: NS:d3dkmthk._D3DKMT_OPENSYNCOBJECTFROMNTHANDLE
title: _D3DKMT_OPENSYNCOBJECTFROMNTHANDLE (d3dkmthk.h)
description: Describes information that is required to map an NT process handle to a graphics processing unit (GPU) synchronization object.
old-location: display\d3dkmt_opensyncobjectfromnthandle.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_OPENSYNCOBJECTFROMNTHANDLE structure"]
ms.keywords: D3DKMT_OPENSYNCOBJECTFROMNTHANDLE, D3DKMT_OPENSYNCOBJECTFROMNTHANDLE structure [Display Devices], _D3DKMT_OPENSYNCOBJECTFROMNTHANDLE, d3dkmthk/D3DKMT_OPENSYNCOBJECTFROMNTHANDLE, display.d3dkmt_opensyncobjectfromnthandle
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
req.typenames: D3DKMT_OPENSYNCOBJECTFROMNTHANDLE
f1_keywords:
 - _D3DKMT_OPENSYNCOBJECTFROMNTHANDLE
 - d3dkmthk/_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE
 - D3DKMT_OPENSYNCOBJECTFROMNTHANDLE
 - d3dkmthk/D3DKMT_OPENSYNCOBJECTFROMNTHANDLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmthk.h
api_name:
 - _D3DKMT_OPENSYNCOBJECTFROMNTHANDLE
 - D3DKMT_OPENSYNCOBJECTFROMNTHANDLE
---

# _D3DKMT_OPENSYNCOBJECTFROMNTHANDLE structure


## -description

Describes information that is required to map an NT process handle to a graphics processing unit (GPU) synchronization object.

## -struct-fields

### -field hNtHandle [in]

An NT handle to the process.

### -field hSyncObject [out]

A handle of type <b>D3DKMT_HANDLE</b> that represents a kernel-mode handle to the kernel-mode synchronization object.

