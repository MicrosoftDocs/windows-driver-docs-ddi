---
UID: NC:d3dumddi.PFND3DDDI_VOLBLT1
title: PFND3DDDI_VOLBLT1 (d3dumddi.h)
description: Performs a bit-block transfer (bitblt) operation from a source volume texture to a destination volume texture. Implemented by Windows Display Driver Model (WDDM) 1.2 or later user-mode display drivers.
old-location: display\volblt1.htm
tech.root: display
ms.assetid: 81B9AB74-9CD1-4181-BE13-32D519069FD4
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_VOLBLT1, PFND3DDDI_VOLBLT1 callback, VolBlt1, VolBlt1 callback function [Display Devices], d3dumddi/VolBlt1, display.volblt1
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dumddi.h
api_name:
- VolBlt1
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_VOLBLT1 callback function


## -description


Performs a bit-block transfer (bitblt) operation from a source volume texture to a destination volume texture. Implemented by Windows Display Driver Model (WDDM) 1.2 or later user-mode display drivers.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh451145">D3DDDIARG_VOLUMEBLT1</a> structure that defines the parameters for the volume bitblt operation.


## -returns




      Returns S_OK or an appropriate error result if the volume bitblt operation is not successfully performed.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451145">D3DDDIARG_VOLUMEBLT1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 

