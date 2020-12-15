---
UID: NS:d3dumddi._D3DDDIARG_OPENADAPTER
title: _D3DDDIARG_OPENADAPTER (d3dumddi.h)
description: The D3DDDIARG_OPENADAPTER structure contains information that describes the graphics adapter object.
old-location: display\d3dddiarg_openadapter.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDIARG_OPENADAPTER structure"]
ms.keywords: D3DDDIARG_OPENADAPTER, D3DDDIARG_OPENADAPTER structure [Display Devices], UMDisplayDriver_param_Structs_6b07c27c-40f3-497c-ba20-53a19a003ea6.xml, _D3DDDIARG_OPENADAPTER, d3dumddi/D3DDDIARG_OPENADAPTER, display.d3dddiarg_openadapter
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
req.typenames: D3DDDIARG_OPENADAPTER
f1_keywords:
 - _D3DDDIARG_OPENADAPTER
 - d3dumddi/_D3DDDIARG_OPENADAPTER
 - D3DDDIARG_OPENADAPTER
 - d3dumddi/D3DDDIARG_OPENADAPTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDIARG_OPENADAPTER
---

# _D3DDDIARG_OPENADAPTER structure


## -description

The D3DDDIARG_OPENADAPTER structure contains information that describes the graphics adapter object.

## -struct-fields

### -field hAdapter

[in/out] A handle to the graphics adapter object. On input to the <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_openadapter">OpenAdapter</a> function, <b>hAdapter</b> specifies the handle that the driver should use to query for graphics adapter capabilities when the driver calls the Microsoft Direct3D runtime-supplied <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_queryadapterinfocb">pfnQueryAdapterInfoCb</a> callback function. 

The driver generates a unique handle and passes it back to the Direct3D runtime. On output from the <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_openadapter">OpenAdapter</a> function, <b>hAdapter</b> specifies the handle that the Direct3D runtime uses in subsequent driver calls to identify the graphics adapter object.

### -field Interface

[in] The Direct3D/DirectDraw interface version (for example, 7, 8, or 9) that opens the graphics adapter.

### -field Version

[in] A number that the driver can use to identify when the Direct3D/DirectDraw runtime was built. For example, the driver can use the version number to differentiate between a runtime that is released with Windows Vista and a runtime that is released with a subsequent service pack, which might contain a fix that the driver requires.

### -field pAdapterCallbacks

[in] A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_adaptercallbacks">D3DDDI_ADAPTERCALLBACKS</a> structure that contains the Direct3D runtime-supplied <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_queryadapterinfocb">pfnQueryAdapterInfoCb</a> callback function that the driver can use.

### -field pAdapterFuncs

[out] A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_adapterfuncs">D3DDDI_ADAPTERFUNCS</a> structure that contains a table of user-mode display driver adapter-specific functions. The Direct3D runtime uses these functions to communicate with the user-mode display driver about operations that are specific to the graphics adapter.

### -field DriverVersion

[out] The version of the Direct3D user-mode display driver's interface, which was obtained from the <i>D3dumddi.h</i> header file, that the driver was compiled with. The user-mode display driver should return D3D_UMD_INTERFACE_VERSION. 

<div class="alert"><b>Note</b>  If a user-mode driver does not support Windows 7 features (DXGKDDI_INTERFACE_VERSION < DXGKDDI_INTERFACE_VERSION_WIN7), and you want to compile the driver
with the Windows 7 WDK (Version 7600), make sure that the driver returns D3D_UMD_INTERFACE_VERSION_VISTA.</div>
<div> </div>

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_adaptercallbacks">D3DDDI_ADAPTERCALLBACKS</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_adapterfuncs">D3DDDI_ADAPTERFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_openadapter">OpenAdapter</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_queryadapterinfocb">pfnQueryAdapterInfoCb</a>
