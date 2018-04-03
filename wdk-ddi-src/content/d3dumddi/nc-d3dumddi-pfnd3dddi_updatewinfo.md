---
UID: NC:d3dumddi.PFND3DDDI_UPDATEWINFO
title: PFND3DDDI_UPDATEWINFO
author: windows-driver-content
description: The UpdateWInfo function updates the w range for w buffering.
old-location: display\updatewinfo.htm
old-project: display
ms.assetid: e9cd87b9-3958-4b10-895d-480e03ebea76
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3DDDI_UPDATEWINFO, UpdateWInfo, UpdateWInfo callback function [Display Devices], UserModeDisplayDriver_Functions_c829f8ef-b1fd-49ef-a9f0-cf92232bdb4f.xml, d3dumddi/UpdateWInfo, display.updatewinfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	UpdateWInfo
product:
- Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_UPDATEWINFO callback


## -description


The <i>UpdateWInfo</i> function updates the w range for w buffering.


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544124">D3DDDIARG_WINFO</a> structure that describes the w range for w buffering.


## -returns



<i>UpdateWInfo</i> returns S_OK or an appropriate error result if the w range is not successfully updated.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544124">D3DDDIARG_WINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 

