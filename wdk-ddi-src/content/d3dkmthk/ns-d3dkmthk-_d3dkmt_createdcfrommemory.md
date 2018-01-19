---
UID: NS:d3dkmthk._D3DKMT_CREATEDCFROMMEMORY
title: _D3DKMT_CREATEDCFROMMEMORY
author: windows-driver-content
description: The D3DKMT_CREATEDCFROMMEMORY structure describes parameters for creating the display context.
old-location: display\d3dkmt_createdcfrommemory.htm
old-project: display
ms.assetid: 260fd894-fc5a-4a27-ac35-3f1b145b52b7
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMT_CREATEDCFROMMEMORY, D3DKMT_CREATEDCFROMMEMORY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_CREATEDCFROMMEMORY
req.alt-loc: d3dkmthk.h
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
req.typenames: D3DKMT_CREATEDCFROMMEMORY
---

# _D3DKMT_CREATEDCFROMMEMORY structure



## -description
The D3DKMT_CREATEDCFROMMEMORY structure describes parameters for creating the display context.



## -syntax

````
typedef struct _D3DKMT_CREATEDCFROMMEMORY {
  VOID         *pMemory;
  D3DDDIFORMAT Format;
  UINT         Width;
  UINT         Height;
  UINT         Pitch;
  HDC          hDeviceDc;
  PALETTEENTRY *pColorTable;
  HDC          hDc;
  HANDLE       hBitmap;
} D3DKMT_CREATEDCFROMMEMORY;
````


## -struct-fields

### -field pMemory

[in] A pointer to a block of memory for the display context.


### -field Format

[in] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>-typed value that indicates the pixel format for the memory block that <b>pMemory</b> points to.


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


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>
</dt>
<dt>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatedcfrommemory.md">D3DKMTCreateDCFromMemory</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_CREATEDCFROMMEMORY structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

