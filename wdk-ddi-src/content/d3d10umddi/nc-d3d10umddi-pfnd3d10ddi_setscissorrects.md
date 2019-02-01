---
UID: NC:d3d10umddi.PFND3D10DDI_SETSCISSORRECTS
title: PFND3D10DDI_SETSCISSORRECTS (d3d10umddi.h)
description: The SetScissorRects function marks portions of render targets that rendering is confined to.
old-location: display\setscissorrects.htm
ms.assetid: ef61f50b-a82b-43df-865f-2f9d9ca906d4
ms.date: 05/10/2018
ms.keywords: PFND3D10DDI_SETSCISSORRECTS, PFND3D10DDI_SETSCISSORRECTS callback, SetScissorRects, SetScissorRects callback function [Display Devices], UserModeDisplayDriverDx10_Functions_c1eec8b9-134e-4066-9f31-d1693e0c4b66.xml, d3d10umddi/SetScissorRects, display.setscissorrects
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
-	d3d10umddi.h
api_name:
-	SetScissorRects
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_SETSCISSORRECTS callback function


## -description


The <i>SetScissorRects</i> function marks portions of render targets that rendering is confined to.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param NumRects

[in] The total number of render-target portions that the <i>pRects</i> parameter specifies. 

### -param ClearRects

[in] The number of render-target portions after the number of render-target portions that <i>NumScissorRects </i>specifies to be set to <b>NULL</b>. This number represents the difference between the previous number of render-target portions (that is, when the Microsoft Direct3D runtime previously called <i>SetScissorRects</i>) and the new number of render-target portions. 

Note that the number that <i>ClearScissorRects</i> specifies is only an optimization aid because the user-mode display driver could calculate this number. 


### -param *

*pRects* [in]

An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structures for the render-target portions to mark. 



## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The D3D10_DDI_RECT structure is defined as a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure.

```cpp
typedef RECT D3D10_DDI_RECT;
```

The user-mode display driver must set all render-target portions atomically as one operation. 

Although the <i>NumScissorRects</i> parameter specifies the number of render-target portions in the array that the <i>pRects</i> parameter specifies, some values in the array can be <b>NULL</b>. 

The range of render-target portions between the number that <i>NumScissorRects</i> specifies and the maximum number of render-target portions that are allowed is required to contain all <b>NULL</b> or unbound values. The number that the <i>ClearScissorRects</i> parameter specifies informs the driver about how many render-target portions the driver must clear out for the current atomic operation. 

If the previous call to <i>SetScissorRects</i> passed a value of 2 in the <i>NumScissorRects</i> parameter and the current call to <i>SetScissorRects</i> passes a value of 4 in <i>NumScissorRects</i>, the current call to <i>SetScissorRects</i> also passes a value of 0 in the <i>ClearScissorRects</i> parameter. If the next successive call to <i>SetScissorRects</i> passes a value of 1 in <i>NumScissorRects</i>, the successive call also passes a value of 3 (4 - 1) in <i>ClearScissorRects</i>.

When the value of clear render-target portions is requested during user-mode query operations, the value is the difference between the maximum number of render-target portions and the render-target portions value.

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function, the Microsoft Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>SetScissorRects</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

