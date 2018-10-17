---
UID: NS:d3dhal._D3DHAL_DP2ADDDIRTYBOX
title: "_D3DHAL_DP2ADDDIRTYBOX"
author: windows-driver-content
description: DirectX 8.1 and later versions only. D3DHAL_DP2ADDDIRTYBOX is used to specify that a portion of a 3D resource--a volume texture--was dirtied in system memory. Therefore, this volume must be reloaded into video memory before being used.
old-location: display\d3dhal_dp2adddirtybox.htm
tech.root: display
ms.assetid: 9cb74a6f-64ae-449a-a1de-6b05419e3387
ms.date: 5/10/2018
ms.keywords: "*LPD3DHAL_DP2ADDDIRTYBOX, D3DHAL_DP2ADDDIRTYBOX, D3DHAL_DP2ADDDIRTYBOX structure [Display Devices], LPD3DHAL_DP2ADDDIRTYBOX, LPD3DHAL_DP2ADDDIRTYBOX structure pointer [Display Devices], _D3DHAL_DP2ADDDIRTYBOX, d3dhal/D3DHAL_DP2ADDDIRTYBOX, d3dhal/LPD3DHAL_DP2ADDDIRTYBOX, d3dstrct_ae7da3ce-63e0-4854-ad22-12b2669baba2.xml, display.d3dhal_dp2adddirtybox"
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dhal.h
api_name:
-	D3DHAL_DP2ADDDIRTYBOX
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2ADDDIRTYBOX
---

# _D3DHAL_DP2ADDDIRTYBOX structure


## -description



   DirectX 8.1 and later versions only.
   

D3DHAL_DP2ADDDIRTYBOX is used to specify that a portion of a 3D resource--a volume texture--was dirtied in system memory. Therefore, this volume must be reloaded into video memory before being used. 


## -struct-fields




### -field dwSurface

Specifies the handle to the managed 3D resource that contains a dirtied volume texture.


### -field DirtyBox

Specifies the volume texture that was marked as dirtied. This is a D3DBOX structure, which is described in the Microsoft Windows SDK documentation. 


## -remarks



D3DHAL_DP2ADDDIRTYBOX, along with the DP2OP_ADDDIRTYBOX token, is used only for driver managed resources. D3DHAL_DP2ADDDIRTYBOX is never sent unless the driver indicates that it manages resources. To indicate that it manages resources, the driver must set the DDCAPS2_CANMANAGERESOURCE bit, in addition to the DDCAPS2_CANMANAGETEXTURE bit, in the <b>dwCaps2</b> member of a DDCORECAPS structure. The driver specifies this <a href="https://msdn.microsoft.com/library/windows/hardware/ff549248">DDCORECAPS</a> structure in the <b>ddCaps</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551627">DD_HALINFO</a> structure when the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556229">DrvGetDirectDrawInfo</a> function is called to initialize the DirectDraw component of the driver.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545678">D3DHAL_DP2OPERATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549248">DDCORECAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551627">DD_HALINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556229">DrvGetDirectDrawInfo</a>
 

 

