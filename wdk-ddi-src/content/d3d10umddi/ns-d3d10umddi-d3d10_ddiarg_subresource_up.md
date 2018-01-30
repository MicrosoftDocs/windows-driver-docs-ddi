---
UID: NS:d3d10umddi.D3D10_DDIARG_SUBRESOURCE_UP
title: D3D10_DDIARG_SUBRESOURCE_UP
author: windows-driver-content
description: The D3D10_DDIARG_SUBRESOURCE_UP structure describes initialization information about a subresource.
old-location: display\d3d10_ddiarg_subresource_up.htm
old-project: display
ms.assetid: 035ce56c-b2a0-4ee0-83ce-4a45f05e5ff4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: UMDisplayDriver_Dx10param_Structs_4bc98700-ad44-4b40-9fc2-b40eeae79626.xml, D3D10_DDIARG_SUBRESOURCE_UP structure [Display Devices], display.d3d10_ddiarg_subresource_up, d3d10umddi/D3D10_DDIARG_SUBRESOURCE_UP, D3D10_DDIARG_SUBRESOURCE_UP
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3d10umddi.h
apiname:
-	D3D10_DDIARG_SUBRESOURCE_UP
product: Windows
targetos: Windows
req.typenames: D3D10_DDIARG_SUBRESOURCE_UP
---

# D3D10_DDIARG_SUBRESOURCE_UP structure


## -description


The D3D10_DDIARG_SUBRESOURCE_UP structure describes initialization information about a subresource.


## -syntax


````
typedef struct D3D10_DDIARG_SUBRESOURCE_UP {
  VOID *pSysMem;
  UINT SysMemPitch;
  UINT SysMemSlicePitch;
} D3D10_DDIARG_SUBRESOURCE_UP;
````


## -struct-fields




### -field pSysMem

[in] A pointer to a buffer that contains the contents of the subresource to copy from. 


### -field SysMemPitch

[in] The pitch, in bytes, of the surface--that is, the distance, in bytes, to the start of the next row.


### -field SysMemSlicePitch

[in] The pitch, in bytes, of the depth slice--that is, the distance, in bytes, to the start of the next depth, where a 3-D subresource is composed of width x rows x depth.  


## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createresource.md">D3D10DDIARG_CREATERESOURCE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_DDIARG_SUBRESOURCE_UP structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

