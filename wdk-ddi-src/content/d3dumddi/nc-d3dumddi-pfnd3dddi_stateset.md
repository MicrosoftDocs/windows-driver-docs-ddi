---
UID: NC:d3dumddi.PFND3DDDI_STATESET
title: PFND3DDDI_STATESET
author: windows-driver-content
description: The StateSet function sets a state block.
old-location: display\stateset.htm
old-project: display
ms.assetid: 2c298de6-a3d9-45c7-ab60-dc9124eed1bb
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3DDDI_STATESET, StateSet, StateSet callback function [Display Devices], UserModeDisplayDriver_Functions_ca9843ce-a32d-4d81-844a-213b7fe6c6e0.xml, d3dumddi/StateSet, display.stateset
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
-	StateSet
product:
- Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_STATESET callback


## -description


The <i>StateSet</i> function sets a state block.


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543380">D3DDDIARG_STATESET</a> structure that describes how to set the state block.


## -returns



<i>StateSet</i> returns S_OK or an appropriate error result if the state block is not successfully set.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543380">D3DDDIARG_STATESET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 

