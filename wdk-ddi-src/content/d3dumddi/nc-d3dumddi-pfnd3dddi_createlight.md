---
UID: NC:d3dumddi.PFND3DDDI_CREATELIGHT
title: PFND3DDDI_CREATELIGHT
author: windows-driver-content
description: The CreateLight function creates a light source.
old-location: display\createlight.htm
tech.root: display
ms.assetid: 4649b1d1-6fd3-48fb-b25f-1228851bb682
ms.date: 5/10/2018
ms.keywords: CreateLight, CreateLight callback function [Display Devices], PFND3DDDI_CREATELIGHT, PFND3DDDI_CREATELIGHT callback, UserModeDisplayDriver_Functions_c6b9e247-5a6b-4e90-bcbd-bc02708ca555.xml, d3dumddi/CreateLight, display.createlight
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
-	CreateLight
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_CREATELIGHT callback function


## -description


The <b>CreateLight</b> function creates a light source.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542943">D3DDDIARG_CREATELIGHT</a> structure that contains the index into the light array.


## -returns



<b>CreateLight</b> should return S_OK or an appropriate error result if it cannot successfully create a light source.




## -remarks



The user-mode display driver should enlarge its light array as necessary to accommodate at least as many light sources as specified by the <b>Index</b> member in <a href="https://msdn.microsoft.com/library/windows/hardware/ff542943">D3DDDIARG_CREATELIGHT</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542943">D3DDDIARG_CREATELIGHT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 

