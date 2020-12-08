---
UID: NS:d3dumddi._D3DDDIARG_DESTROYAUTHENICATEDCHANNEL
title: _D3DDDIARG_DESTROYAUTHENICATEDCHANNEL (d3dumddi.h)
description: The D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL structure contains the handle to an authenticated channel that is destroyed in a call to the DestroyAuthenticatedChannel function.
old-location: display\d3dddiarg_destroyauthenticatedchannel.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDIARG_DESTROYAUTHENICATEDCHANNEL structure"]
ms.keywords: D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL, D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL structure [Display Devices], UMDisplayDriver_param_Structs_be6187b3-2d01-450e-90a7-d01a97aba764.xml, _D3DDDIARG_DESTROYAUTHENICATEDCHANNEL, d3dumddi/D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL, display.d3dddiarg_destroyauthenticatedchannel
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL is supported beginning with the Windows 7 operating system.
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
req.typenames: D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL
f1_keywords:
 - _D3DDDIARG_DESTROYAUTHENICATEDCHANNEL
 - d3dumddi/_D3DDDIARG_DESTROYAUTHENICATEDCHANNEL
 - D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL
 - d3dumddi/D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL
---

# _D3DDDIARG_DESTROYAUTHENICATEDCHANNEL structure


## -description

The D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL structure contains the handle to an authenticated channel that is destroyed in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_destroyauthenticatedchannel">DestroyAuthenticatedChannel</a> function.

## -struct-fields

### -field hChannel

[in] The handle to the authenticated channel that the driver destroys.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_destroyauthenticatedchannel">DestroyAuthenticatedChannel</a>
