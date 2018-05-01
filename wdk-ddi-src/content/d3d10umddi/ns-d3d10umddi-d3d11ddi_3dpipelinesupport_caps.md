---
UID: NS:d3d10umddi.D3D11DDI_3DPIPELINESUPPORT_CAPS
title: D3D11DDI_3DPIPELINESUPPORT_CAPS
author: windows-driver-content
description: The D3D11DDI_3DPIPELINESUPPORT_CAPS structure contains display device pipeline capabilities.
old-location: display\d3d11ddi_3dpipelinesupport_caps.htm
old-project: display
ms.assetid: 69bafa36-2f99-4c6f-b5ed-99a7030b22e6
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3D11DDI_3DPIPELINESUPPORT_CAPS, D3D11DDI_3DPIPELINESUPPORT_CAPS structure [Display Devices], UMDisplayDriver_Dx11param_Structs_dc9a2de4-8fcf-4cd4-9c59-cc57941cab00.xml, d3d10umddi/D3D11DDI_3DPIPELINESUPPORT_CAPS, display.d3d11ddi_3dpipelinesupport_caps
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDI_3DPIPELINESUPPORT_CAPS is supported beginning with the Windows 7 operating system.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d10umddi.h
api_name:
-	D3D11DDI_3DPIPELINESUPPORT_CAPS
product: Windows
targetos: Windows
req.typenames: D3D11DDI_3DPIPELINESUPPORT_CAPS
---

# D3D11DDI_3DPIPELINESUPPORT_CAPS structure


## -description


The D3D11DDI_3DPIPELINESUPPORT_CAPS structure contains display device pipeline capabilities. 


## -struct-fields




### -field Caps

[in] A value that identifies the pipeline capabilities of the driver. 


## -remarks



The driver uses the one of the values from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542126">D3D11DDI_3DPIPELINELEVEL</a> enumeration and the following macro to encode the 3-D pipeline level:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define D3D11DDI_ENCODE_3DPIPELINESUPPORT_CAP( Level ) (0x1 &lt;&lt; Level)</pre>
</td>
</tr>
</table></span></div>
The driver then uses the macro's result in the <b>Caps</b> member of the D3D11DDI_3DPIPELINESUPPORT_CAPS structure to provide information to the Direct3D runtime when the runtime calls the driver's <a href="https://msdn.microsoft.com/83cd5f34-5f12-4ead-ad33-366fc3c6e804">GetCaps(D3D10_2)</a> function with the <b>Type</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff541887">D3D10_2DDIARG_GETCAPS</a> set to D3D11DDICAPS_3DPIPELINESUPPORT.

The driver uses the following constant and macros to extract one of the values from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542126">D3D11DDI_3DPIPELINELEVEL</a> enumeration that represents the 3-D pipeline level to set for a display device. The driver extracts the value from the <b>Caps</b> member of the D3D11DDI_3DPIPELINESUPPORT_CAPS structure. The driver uses the 3-D pipeline level to create the appropriate display device when the driver receives a call to its <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> function.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_SHIFT (0x1)
#define D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_MASK (0x7 &lt;&lt; D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_SHIFT)
#define D3D11DDI_EXTRACT_3DPIPELINELEVEL_FROM_FLAGS( Flags ) \
    ((D3D11DDI_3DPIPELINELEVEL)(((Flags) &amp; D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_MASK) &gt;&gt; \
    D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_SHIFT))</pre>
</td>
</tr>
</table></span></div>
For more information about the Direct3D version 10 pipeline, see <a href="https://msdn.microsoft.com/63672d6e-5c5d-4873-a104-991e0b17d128">Rendering Pipeline</a>. 

For more information about the Direct3D version 11 pipelines, see <a href="https://msdn.microsoft.com/7d724751-761e-409c-8398-d1b5d58c057c">Pipelines for Direct3D Version 11</a>.




## -see-also




<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541894">D3D10_2DDICAPS_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542126">D3D11DDI_3DPIPELINELEVEL</a>



<a href="https://msdn.microsoft.com/83cd5f34-5f12-4ead-ad33-366fc3c6e804">GetCaps(D3D10_2)</a>
 

 

