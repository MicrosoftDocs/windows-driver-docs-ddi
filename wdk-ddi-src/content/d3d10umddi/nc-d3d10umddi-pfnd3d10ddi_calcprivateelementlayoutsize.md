---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATEELEMENTLAYOUTSIZE
title: PFND3D10DDI_CALCPRIVATEELEMENTLAYOUTSIZE
author: windows-driver-content
description: The CalcPrivateElementLayoutSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for an element layout.
old-location: display\calcprivateelementlayoutsize.htm
old-project: display
ms.assetid: 9fc80cea-8e4a-467a-b232-74333d2ceb5f
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.calcprivateelementlayoutsize, CalcPrivateElementLayoutSize callback function [Display Devices], CalcPrivateElementLayoutSize, PFND3D10DDI_CALCPRIVATEELEMENTLAYOUTSIZE, PFND3D10DDI_CALCPRIVATEELEMENTLAYOUTSIZE, d3d10umddi/CalcPrivateElementLayoutSize, UserModeDisplayDriverDx10_Functions_7c153781-eabd-4f5e-b949-0ac5c9e0d94b.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3d10umddi.h
apiname:
-	CalcPrivateElementLayoutSize
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_CALCPRIVATEELEMENTLAYOUTSIZE callback


## -description


The <i>CalcPrivateElementLayoutSize</i> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for an element layout.


## -prototype


````
PFND3D10DDI_CALCPRIVATEELEMENTLAYOUTSIZE CalcPrivateElementLayoutSize;

SIZE_T APIENTRY CalcPrivateElementLayoutSize(
  _In_       D3D10DDI_HDEVICE                hDevice,
  _In_ const D3D10DDIARG_CREATEELEMENTLAYOUT *pCreateElementLayout
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE



### -param *






#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pCreateElementLayout [in]

 A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createelementlayout.md">D3D10DDIARG_CREATEELEMENTLAYOUT</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region. 


## -returns


<i>CalcPrivateElementLayoutSize</i> returns the size of the memory region that the driver requires for creating an element layout.



## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createelementlayout.md">D3D10DDIARG_CREATEELEMENTLAYOUT</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_CALCPRIVATEELEMENTLAYOUTSIZE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

