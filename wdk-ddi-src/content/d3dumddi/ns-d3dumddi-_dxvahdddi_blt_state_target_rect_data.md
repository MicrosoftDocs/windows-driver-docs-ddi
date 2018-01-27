---
UID: NS:d3dumddi._DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA
title: _DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA
author: windows-driver-content
description: The DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA structure describes data that specifies the target rectangle of the output.
old-location: display\dxvahdddi_blt_state_target_rect_data.htm
old-project: display
ms.assetid: d6b76b6b-59d9-441f-846e-fe89d26f631d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA, display.dxvahdddi_blt_state_target_rect_data, DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA structure [Display Devices], DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA, d3dumddi/DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA, DXVA2_Structs_bb978cee-d80a-429b-ac2c-1704539c55f7.xml
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	d3dumddi.h
apiname: 
-	DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA
product: Windows
targetos: Windows
req.typenames: DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA
---

# _DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA structure


## -description


The DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA structure describes data that specifies the target rectangle of the output. 


## -syntax


````
typedef struct _DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA {
  BOOL Enable;
  RECT TargetRect;
} DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA;
````


## -struct-fields




### -field Enable

[in] A Boolean value that specifies whether the driver should use the <b>TargetRect</b> member or the entire output surface as the target. The default value is <b>FALSE</b>, which indicates that the entire output surface is the target. 


### -field TargetRect

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that specifies the target rectangle in the coordinates of the output surface. This member is relevant only when the <b>Enable</b> member is set to <b>TRUE</b>. The default value is (0,0,0,0).


## -remarks


If the <b>Enable</b> member is set to <b>TRUE</b> and the target rectangle that the <b>TargetRect</b> member specifies is not within the output surface, the intersection of the target rectangle and the output surface is used as the target rectangle. 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

