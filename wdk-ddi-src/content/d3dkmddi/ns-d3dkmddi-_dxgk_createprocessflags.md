---
UID: NS:d3dkmddi._DXGK_CREATEPROCESSFLAGS
title: _DXGK_CREATEPROCESSFLAGS
author: windows-driver-content
description: DXGK_CREATEPROCESSFLAGS is used with DXGKARG_CREATEPROCESS and DxgkDdiCreateProcess to create a kernel mode driver object for a Microsoft DirectX graphics kernel process object.
old-location: display\dxgk_createprocessflags.htm
old-project: display
ms.assetid: 43B8202C-6AC1-4596-BA85-FEB9FB0B5746
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_CREATEPROCESSFLAGS, DXGK_CREATEPROCESSFLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_CREATEPROCESSFLAGS
req.alt-loc: d3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: DXGK_CREATEPROCESSFLAGS
---

# _DXGK_CREATEPROCESSFLAGS structure



## -description
<b>DXGK_CREATEPROCESSFLAGS</b> is used with <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createprocess.md">DXGKARG_CREATEPROCESS</a> and <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createprocess.md">DxgkDdiCreateProcess</a> to create a kernel mode driver object for a Microsoft DirectX graphics kernel process object.



## -syntax

````
typedef struct _DXGK_CREATEPROCESSFLAGS {
  union {
    struct {
      UINT SystemProcess  :1;
      UINT GdiProcess  :1;
      UINT Reserved  :30;
    };
    UINT   Value;
  };
} DXGK_CREATEPROCESSFLAGS;
````


## -struct-fields

### -field SystemProcess

Indicates that a system process is being created.


### -field GdiProcess

Indicates that a GDI process is being created.


### -field Reserved

This member is reserved and should be set to zero.


### -field Value

The consolidated value of the bitfield members of the structure.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createprocess.md">DXGKARG_CREATEPROCESS</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createprocess.md">DxgkDdiCreateProcess</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_CREATEPROCESSFLAGS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

