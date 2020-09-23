---
UID: NS:d3dkmthk._D3DKMT_CREATEDCFROMMEMORY
title: _D3DKMT_CREATEDCFROMMEMORY (d3dkmthk.h)
description: The D3DKMT_CREATEDCFROMMEMORY structure describes parameters for creating the display context.
old-location: display\d3dkmt_createdcfrommemory.htm
ms.assetid: 260fd894-fc5a-4a27-ac35-3f1b145b52b7
ms.date: 05/10/2018
keywords: ["D3DKMT_CREATEDCFROMMEMORY structure"]
ms.keywords: D3DKMT_CREATEDCFROMMEMORY, D3DKMT_CREATEDCFROMMEMORY structure [Display Devices], OpenGL_Structs_b56e280f-e29b-4781-942a-a36024786d9e.xml, _D3DKMT_CREATEDCFROMMEMORY, d3dkmthk/D3DKMT_CREATEDCFROMMEMORY, display.d3dkmt_createdcfrommemory
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
req.typenames: D3DKMT_CREATEDCFROMMEMORY
f1_keywords:
 - _D3DKMT_CREATEDCFROMMEMORY
 - d3dkmthk/_D3DKMT_CREATEDCFROMMEMORY
 - D3DKMT_CREATEDCFROMMEMORY
 - d3dkmthk/D3DKMT_CREATEDCFROMMEMORY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMT_CREATEDCFROMMEMORY
---

# _D3DKMT_CREATEDCFROMMEMORY structure


## -description

The D3DKMT_CREATEDCFROMMEMORY structure describes parameters for creating the display context.

## -struct-fields

### -field pMemory

[in] A pointer to a block of memory for the display context.

### -field Format

[in] A <a href="/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>-typed value that indicates the pixel format for the memory block that <b>pMemory</b> points to.

### -field Width

[in] The width, in pixels, of the memory block that <b>pMemory</b> points to.

### -field Height

[in] The height, in pixels, of the memory block that <b>pMemory</b> points to.

### -field Pitch

[in] The pitch, in bytes, of the memory block that <b>pMemory</b> points to--that is, the distance in bytes to the start of the next line.

### -field hDeviceDc

[in] A handle to the display context for the device.

### -field pColorTable

[in] An array of 2, 4, 16, or 256 PALETTEENTRY structures that are used to initialize the colors for the memory block that <b>pMemory</b> points to. For more information about PALETTEENTRY, see the Microsoft Window SDK documentation.

### -field hDc

[out] A handle to the display context. The OpenGL runtime generates a handle and passes it back to the driver.

### -field hBitmap

[out] A handle to a bitmap that is related to the display context. The OpenGL runtime generates a handle and passes it back to the driver.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>



<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatedcfrommemory">D3DKMTCreateDCFromMemory</a>