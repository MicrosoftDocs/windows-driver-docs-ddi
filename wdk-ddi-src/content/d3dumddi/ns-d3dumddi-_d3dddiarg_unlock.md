---
UID: NS:d3dumddi._D3DDDIARG_UNLOCK
title: _D3DDDIARG_UNLOCK (d3dumddi.h)
description: The D3DDDIARG_UNLOCK structure describes a resource or a surface within the resource to unlock.
old-location: display\d3dddiarg_unlock.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDIARG_UNLOCK structure"]
ms.keywords: D3DDDIARG_UNLOCK, D3DDDIARG_UNLOCK structure [Display Devices], UMDisplayDriver_param_Structs_ae4773cf-d43a-4468-8d6b-a4c4fa9b55fa.xml, _D3DDDIARG_UNLOCK, d3dumddi/D3DDDIARG_UNLOCK, display.d3dddiarg_unlock
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
req.typenames: D3DDDIARG_UNLOCK
f1_keywords:
 - _D3DDDIARG_UNLOCK
 - d3dumddi/_D3DDDIARG_UNLOCK
 - D3DDDIARG_UNLOCK
 - d3dumddi/D3DDDIARG_UNLOCK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _D3DDDIARG_UNLOCK
 - D3DDDIARG_UNLOCK
---

# _D3DDDIARG_UNLOCK structure


## -description

The D3DDDIARG_UNLOCK structure describes a resource or a surface within the resource to unlock.

## -struct-fields

### -field hResource [in]

A handle to the resource to be unlocked.

### -field SubResourceIndex [in]

The zero-based index into the resource, which is specified by the handle in the <b>hResource</b> member. This index indicates the subresource or surface to be unlocked.

### -field Flags [in]

A <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_unlockflags">D3DDDI_UNLOCKFLAGS</a> structure that indicates, in bit-field flags, how to unlock the resource.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_unlockflags">D3DDDI_UNLOCKFLAGS</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_unlock">Unlock</a>

