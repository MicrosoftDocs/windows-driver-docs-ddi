---
UID: NC:d3dumddi.PFND3DDDI_RENAME
title: PFND3DDDI_RENAME (d3dumddi.h)
description: The Rename function informs a user-mode display driver to start using the renamed allocation that the LockAsync function previously returned for the specified resource.
old-location: display\rename.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_RENAME callback function"]
ms.keywords: PFND3DDDI_RENAME, PFND3DDDI_RENAME callback, Rename, Rename callback function [Display Devices], UserModeDisplayDriver_Functions_50916fb2-ea0e-4143-8588-909a4cd07bec.xml, d3dumddi/Rename, display.rename
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Universal
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
req.typenames: 
f1_keywords:
 - PFND3DDDI_RENAME
 - d3dumddi/PFND3DDDI_RENAME
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - Rename
product:
 - Windows
---

# PFND3DDDI_RENAME callback function


## -description

The <i>Rename</i> function informs a user-mode display driver to start using the renamed allocation that the <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockasync">LockAsync</a> function previously returned for the specified resource.

## -parameters

### -param hDevice

A handle to a display device (that is, the graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_rename">D3DDDIARG_RENAME</a> structure that describes the resource or surface within a resource to rename with a new allocation.

## -returns

<i>Rename</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The resource is successfully renamed.|
|E_OUTOFMEMORY|Rename could not allocate the required memory for it to complete.|

## -remarks

On multiple-processor computers, the Microsoft Direct3D runtime calls the user-mode display driver's <i>Rename</i> function from a worker thread instead of from the main application thread. The runtime calls <i>Rename</i>, at most, once for each successful call to the driver's <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockasync">LockAsync</a> function with the <b>Discard</b> bit-field flag set in the <b>Flags</b> member of the <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_lockasync">D3DDDIARG_LOCKASYNC</a> structure that the <i>pData</i> parameter of <i>LockAsync</i> points to. 

<i>Rename</i> informs the driver to start using the renamed allocation that is specified by the <b>hCookie</b> member of the <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_rename">D3DDDIARG_RENAME</a> structure that the <i>pData</i> parameter of <i>Rename</i> points to. The <b>hCookie</b> handle was previously returned by the <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockasync">LockAsync</a> function if the <b>Discard</b> bit-field flag was set for the locked resource. 

After <i>Rename</i> returns successfully (with S_OK), the user-mode display driver should use the allocation that <b>hCookie</b> specifies for all rendering operations that reference the resource that the <b>hResource</b> and <b>SubResourceIndex</b> members of D3DDDIARG_RENAME specify.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_lockasync">D3DDDIARG_LOCKASYNC</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_rename">D3DDDIARG_RENAME</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockasync">LockAsync</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_rename">Rename</a>
