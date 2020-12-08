---
UID: NE:d3dkmthk._D3DKMT_QUEUEDLIMIT_TYPE
title: _D3DKMT_QUEUEDLIMIT_TYPE (d3dkmthk.h)
description: The D3DKMT_QUEUEDLIMIT_TYPE enumeration type contains values that indicate the type of operations to set or retrieve the queued limit for in a call to the D3DKMTSetQueuedLimit function.
old-location: display\d3dkmt_queuedlimit_type.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_QUEUEDLIMIT_TYPE enumeration"]
ms.keywords: D3DKMT_GET_QUEUEDLIMIT_PRESENT, D3DKMT_QUEUEDLIMIT_TYPE, D3DKMT_QUEUEDLIMIT_TYPE enumeration [Display Devices], D3DKMT_SET_QUEUEDLIMIT_PRESENT, OpenGL_Structs_8908789d-6be7-41de-9aff-526cf8b1684c.xml, _D3DKMT_QUEUEDLIMIT_TYPE, d3dkmthk/D3DKMT_GET_QUEUEDLIMIT_PRESENT, d3dkmthk/D3DKMT_QUEUEDLIMIT_TYPE, d3dkmthk/D3DKMT_SET_QUEUEDLIMIT_PRESENT, display.d3dkmt_queuedlimit_type
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.typenames: D3DKMT_QUEUEDLIMIT_TYPE
f1_keywords:
 - _D3DKMT_QUEUEDLIMIT_TYPE
 - d3dkmthk/_D3DKMT_QUEUEDLIMIT_TYPE
 - D3DKMT_QUEUEDLIMIT_TYPE
 - d3dkmthk/D3DKMT_QUEUEDLIMIT_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMT_QUEUEDLIMIT_TYPE
---

# _D3DKMT_QUEUEDLIMIT_TYPE enumeration


## -description

The D3DKMT_QUEUEDLIMIT_TYPE enumeration type contains values that indicate the type of operations to set or retrieve the queued limit for in a call to the <a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsetqueuedlimit">D3DKMTSetQueuedLimit</a> function.

## -enum-fields

### -field D3DKMT_SET_QUEUEDLIMIT_PRESENT

Indicates to set the limit for the number of present operations that can be queued.

### -field D3DKMT_GET_QUEUEDLIMIT_PRESENT

Indicates to retrieve the limit for the number of present operations that can be queued.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsetqueuedlimit">D3DKMTSetQueuedLimit</a>



<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_setqueuedlimit">D3DKMT_SETQUEUEDLIMIT</a>
