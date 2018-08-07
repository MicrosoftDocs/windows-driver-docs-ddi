---
UID: NS:d3dumddi._DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA
title: "_DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA"
author: windows-driver-content
description: The DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA structure describes data that specifies the target rectangle of the output.
old-location: display\dxvahdddi_blt_state_target_rect_data.htm
tech.root: display
ms.assetid: d6b76b6b-59d9-441f-846e-fe89d26f631d
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DXVA2_Structs_bb978cee-d80a-429b-ac2c-1704539c55f7.xml, DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA, DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA structure [Display Devices], _DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA, d3dumddi/DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA, display.dxvahdddi_blt_state_target_rect_data
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA is supported beginning with the Windows 7 operating system.
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
-	d3dumddi.h
api_name:
-	DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA
product:
- Windows
targetos: Windows
req.typenames: DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA
---

# _DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA structure


## -description


The DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA structure describes data that specifies the target rectangle of the output. 


## -struct-fields




### -field Enable

[in] A Boolean value that specifies whether the driver should use the <b>TargetRect</b> member or the entire output surface as the target. The default value is <b>FALSE</b>, which indicates that the entire output surface is the target. 


### -field TargetRect

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that specifies the target rectangle in the coordinates of the output surface. This member is relevant only when the <b>Enable</b> member is set to <b>TRUE</b>. The default value is (0,0,0,0).


## -remarks



If the <b>Enable</b> member is set to <b>TRUE</b> and the target rectangle that the <b>TargetRect</b> member specifies is not within the output surface, the intersection of the target rectangle and the output surface is used as the target rectangle. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>
 

 

