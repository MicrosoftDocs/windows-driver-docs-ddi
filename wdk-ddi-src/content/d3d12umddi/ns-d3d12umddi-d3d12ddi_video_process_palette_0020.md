---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_PALETTE_0020
title: D3D12DDI_VIDEO_PROCESS_PALETTE_0020
author: windows-driver-content
description: Specifies whether the palette is enabled and an array of palette entries.
old-location: display\d3d12ddi_video_process_palette.htm
old-project: display
ms.assetid: 25AA9012-64A1-4E61-956F-7F30CE0639EA
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3d12umddi/D3D12DDI_VIDEO_PROCESS_PALETTE_0020, D3D12DDI_VIDEO_PROCESS_PALETTE_0020, display.d3d12ddi_video_process_palette, D3D12DDI_VIDEO_PROCESS_PALETTE_0020 structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d12umddi.h
apiname:
-	D3D12DDI_VIDEO_PROCESS_PALETTE_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_PROCESS_PALETTE_0020
---

# D3D12DDI_VIDEO_PROCESS_PALETTE_0020 structure


## -description


Specifies whether the palette is enabled and an array of palette entries. 


## -syntax


````
typedef struct D3D12DDI_VIDEO_PROCESS_PALETTE_0020 {
  BOOL Enable;
  UINT NumEntries;
  UINT *pEntries;
} D3D12DDI_VIDEO_PROCESS_PALETTE_0020;
````


## -struct-fields




### -field Enable

Whether palette is enabled.


### -field NumEntries

The number of elements in the <b>pEntries</b> array.


### -field pEntries

A pointer to an array of palette entries. For RGB streams, the palette entries use the <b>DXGI_FORMAT_B8G8R8A8</b> representation. For YCbCr streams, the palette entries use the <b>DXGI_FORMAT_AYUV</b> representation. For more information, see the <a href="https://msdn.microsoft.com/dce61bc4-4ed5-4e64-84e8-6db88025e5c2">DXGI_FORMAT</a> enumeration. The caller allocates the array.


## -see-also

<a href="https://msdn.microsoft.com/dce61bc4-4ed5-4e64-84e8-6db88025e5c2">DXGI_FORMAT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDI_VIDEO_PROCESS_PALETTE_0020 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

