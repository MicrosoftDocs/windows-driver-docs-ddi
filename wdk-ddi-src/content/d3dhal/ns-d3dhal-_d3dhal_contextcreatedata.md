---
UID: NS:d3dhal._D3DHAL_CONTEXTCREATEDATA
title: _D3DHAL_CONTEXTCREATEDATA (d3dhal.h)
description: The D3DHAL_CONTEXTCREATEDATA structure contains all of the information that the D3dContextCreate function requires to create a new context.
old-location: display\d3dhal_contextcreatedata.htm
tech.root: display
ms.assetid: 9ad169a8-81a7-497c-849a-c36be66caa8e
ms.date: 05/10/2018
keywords: ["D3DHAL_CONTEXTCREATEDATA structure"]
ms.keywords: "*LPD3DHAL_CONTEXTCREATEDATA, D3DHAL_CONTEXTCREATEDATA, D3DHAL_CONTEXTCREATEDATA structure [Display Devices], LPD3DHAL_CONTEXTCREATEDATA, LPD3DHAL_CONTEXTCREATEDATA structure pointer [Display Devices], _D3DHAL_CONTEXTCREATEDATA, d3dhal/D3DHAL_CONTEXTCREATEDATA, d3dhal/LPD3DHAL_CONTEXTCREATEDATA, d3dstrct_46c9dd06-302d-423b-8cd6-fc81a4227ab4.xml, display.d3dhal_contextcreatedata"
req.header: d3dhal.h
req.include-header: D3dhal.h
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
req.typenames: D3DHAL_CONTEXTCREATEDATA
f1_keywords:
 - _D3DHAL_CONTEXTCREATEDATA
 - d3dhal/_D3DHAL_CONTEXTCREATEDATA
 - D3DHAL_CONTEXTCREATEDATA
 - d3dhal/D3DHAL_CONTEXTCREATEDATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dhal.h
api_name:
 - D3DHAL_CONTEXTCREATEDATA
---

# _D3DHAL_CONTEXTCREATEDATA structure


## -description

The D3DHAL_CONTEXTCREATEDATA structure contains all of the information that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_contextcreatecb">D3dContextCreate</a> function requires to create a new context.

## -struct-fields

### -field lpDDGbl

 Driver structure (legacy).

### -field lpDDLcl

Points to the DirectDraw object that an application must create in order to retrieve the COM Interface to Direct3D. This allows context information to be shared between a DirectDraw application and the driver. <b>lpDDLcl</b> is the common and binding factor between the application's context and the driver's context. It points to a <a href="https://docs.microsoft.com/windows/win32/api/ddrawint/ns-ddrawint-dd_directdraw_local">DD_DIRECTDRAW_LOCAL</a> structure that is used to identify the surfaces that belong to a given Direct3D context and is relevant to the current DirectDraw process only. <b>lpDDLcl</b> is necessary because surfaces (for example, depth buffers, rendering buffers, and textures) can be created before a Direct3D context is ever created in the driver.

### -field lpDDS

 Surface to be used as target.

### -field lpDDSLcl

Points to a <a href="https://docs.microsoft.com/windows/win32/api/ddrawint/ns-ddrawint-dd_surface_local">DD_SURFACE_LOCAL</a> structure that describes the DirectDraw surface to be used as the rendering target.

### -field lpDDSZ

Surface to be used as Z.

### -field lpDDSZLcl

Points to a DD_SURFACE_LOCAL structure that describes the DirectDraw surface to be used as a depth buffer. If this member is <b>NULL</b>, no depth buffering is to be performed.

### -field dwPID

Specifies the current process ID. This is the process ID of the Direct3D application that initiated the creation of the Direct3D device.

### -field dwrstates

Points to a render state array that the driver should update when it parses render state commands from the command buffer. The array buffer must be large enough to contain at least the specified number of ULONG values.

### -field dwhContext

Specifies a location that indicates, on input, the version of the Direct3D user-mode runtime and, on output, where the driver returns the context handle upon successfully creating the context. See Remarks for more information.

### -field ddrval

Specifies the location where the driver writes the return code for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_contextcreatecb">D3dContextCreate</a>. A return code of D3D_OK indicates success. A return code of D3DHAL_OUTOFCONTEXTS indicates that the driver cannot create the context. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/return-codes-for-direct3d-driver-callbacks">Return Codes for Direct3D Driver Callbacks</a>.

## -remarks

When the Direct3D runtime calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_contextcreatecb">D3dContextCreate</a> function, the runtime specifies a number that indicates the runtime's user-mode version in the <b>dwhContext</b> member. The following table shows a mapping of numbers and user-mode versions.

|Number|DirectX user-mode version|
|--- |--- |
|5|9.0|
|4|8.0|
|3|7.0|
|2|6.0|
|1|5.0|
|0|3.0|
 

If the driver successfully creates a context, the driver returns the context ID in <b>dwhContext</b> for the Direct3D runtime to use when communicating with the driver.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_contextcreatecb">D3dContextCreate</a>



<a href="https://docs.microsoft.com/windows/win32/api/ddrawint/ns-ddrawint-dd_directdraw_local">DD_DIRECTDRAW_LOCAL</a>



<a href="https://docs.microsoft.com/windows/win32/api/ddrawint/ns-ddrawint-dd_surface_local">DD_SURFACE_LOCAL</a>

