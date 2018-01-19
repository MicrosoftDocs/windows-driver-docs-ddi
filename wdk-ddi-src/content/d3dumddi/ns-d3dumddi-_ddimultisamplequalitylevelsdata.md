---
UID: NS:d3dumddi._DDIMULTISAMPLEQUALITYLEVELSDATA
title: _DDIMULTISAMPLEQUALITYLEVELSDATA
author: windows-driver-content
description: The DDIMULTISAMPLEQUALITYLEVELSDATA structure describes the number of multiple-sample quality levels for a given render-target format.
old-location: display\ddimultisamplequalitylevelsdata.htm
old-project: display
ms.assetid: 48eeea6a-6a1d-43f7-a74c-3ca896c7b2d4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DDIMULTISAMPLEQUALITYLEVELSDATA, DDIMULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DDIMULTISAMPLEQUALITYLEVELSDATA
req.alt-loc: d3dumddi.h
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
req.typenames: DDIMULTISAMPLEQUALITYLEVELSDATA
---

# _DDIMULTISAMPLEQUALITYLEVELSDATA structure



## -description
The DDIMULTISAMPLEQUALITYLEVELSDATA structure describes the number of multiple-sample quality levels for a given render-target format.



## -syntax

````
typedef struct _DDIMULTISAMPLEQUALITYLEVELSDATA {
  D3DDDIFORMAT           Format;
  BOOL                   Flip;
  D3DDDIMULTISAMPLE_TYPE MsType;
  UINT                   QualityLevels;
} DDIMULTISAMPLEQUALITYLEVELSDATA;
````


## -struct-fields

### -field Format

[in] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>-typed value that indicates the surface format of the multiple-sampled render target.


### -field Flip

[in] A Boolean value that specifies whether the resolution is flip or bit-block transfer (blt) style. <b>TRUE</b> indicates flip-style resolution; <b>FALSE</b> indicates blt-style resolution.


### -field MsType

[in] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddimultisample_type.md">D3DDDIMULTISAMPLE_TYPE</a>-typed value that indicates the level of full-scene multiple sampling. If the display device supports maskable multiple sampling (that is, more than one sample for a multiple-sample render-target format plus antialias support), the user-mode display driver must provide the number of quality levels for the D3DDDIMULTISAMPLE_NONMASKABLE (1) value.


### -field QualityLevels

[in] The number of multiple-sample quality levels that the user-mode display driver supports for the render-target format that is specified by the <b>Format</b>, <b>bFlip</b>, and <b>MSType</b> members.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaps.md">D3DDDIARG_GETCAPS</a>
</dt>
<dt>
<a href="..\d3dumddi\ne-d3dumddi-_d3dddicaps_type.md">D3DDDICAPS_TYPE</a>
</dt>
<dt>
<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>
</dt>
<dt>
<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddimultisample_type.md">D3DDDIMULTISAMPLE_TYPE</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DDIMULTISAMPLEQUALITYLEVELSDATA structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

