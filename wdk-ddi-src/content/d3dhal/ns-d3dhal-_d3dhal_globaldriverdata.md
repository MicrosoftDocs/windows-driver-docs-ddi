---
UID: NS:d3dhal._D3DHAL_GLOBALDRIVERDATA
title: _D3DHAL_GLOBALDRIVERDATA
author: windows-driver-content
description: The D3DHAL_GLOBALDRIVERDATA structure specifies the 3D capabilities of the driver and its device.
old-location: display\d3dhal_globaldriverdata.htm
old-project: display
ms.assetid: 4aba7417-8391-4ae7-a449-dbc307cab530
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DHAL_GLOBALDRIVERDATA, D3DHAL_GLOBALDRIVERDATA, *LPD3DHAL_GLOBALDRIVERDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DHAL_GLOBALDRIVERDATA
req.alt-loc: d3dhal.h
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
req.typenames: D3DHAL_GLOBALDRIVERDATA
---

# _D3DHAL_GLOBALDRIVERDATA structure



## -description
The D3DHAL_GLOBALDRIVERDATA structure specifies the 3D capabilities of the driver and its device.



## -syntax

````
typedef struct _D3DHAL_GLOBALDRIVERDATA {
  DWORD            dwSize;
  D3DDEVICEDESC_V1 hwCaps;
  DWORD            dwNumVertices;
  DWORD            dwNumClipVertices;
  DWORD            dwNumTextureFormats;
  LPDDSURFACEDESC  lpTextureFormats;
} D3DHAL_GLOBALDRIVERDATA, *LPD3DHAL_GLOBALDRIVERDATA;
````


## -struct-fields

### -field dwSize

Specifies the size in bytes of this D3DHAL_GLOBALDRIVERDATA structure.


### -field hwCaps

Specifies a <a href="..\d3dhal\ns-d3dhal-_d3ddevicedesc_v1.md">D3DDEVICEDESC_V1</a> structure where the driver should return its hardware capabilities.


### -field dwNumVertices

Reserved for system use and should be set to zero by the driver.


### -field dwNumClipVertices

Reserved for system use and should be set to zero by the driver.


### -field dwNumTextureFormats

Specifies the number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff550339">DDSURFACEDESC</a> structures that <b>lpTextureFormats</b> points to.


### -field lpTextureFormats

Points to an array of DDSURFACEDESC structures where the driver should return the texture formats supported by the device.


## -remarks
The driver is responsible for allocating space for and setting all members of this structure. The driver returns a pointer to this structure in the <b>lpD3DGlobalDriverData</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551627">DD_HALINFO</a> structure, which is passed to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556229">DrvGetDirectDrawInfo</a> function during driver initialization.


## -see-also
<dl>
<dt>
<a href="..\d3dhal\ns-d3dhal-_d3ddevicedesc_v1.md">D3DDEVICEDESC_V1</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551627">DD_HALINFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550339">DDSURFACEDESC</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556229">DrvGetDirectDrawInfo</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_GLOBALDRIVERDATA structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

