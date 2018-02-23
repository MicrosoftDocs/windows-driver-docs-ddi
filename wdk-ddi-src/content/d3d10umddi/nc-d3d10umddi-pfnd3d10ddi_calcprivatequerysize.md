---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATEQUERYSIZE
title: PFND3D10DDI_CALCPRIVATEQUERYSIZE
author: windows-driver-content
description: The CalcPrivateQuerySize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a query.
old-location: display\calcprivatequerysize.htm
old-project: display
ms.assetid: 59a59aa8-085e-4bf8-8a6f-e08f2aecd894
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: display.calcprivatequerysize, CalcPrivateQuerySize callback function [Display Devices], CalcPrivateQuerySize, PFND3D10DDI_CALCPRIVATEQUERYSIZE, PFND3D10DDI_CALCPRIVATEQUERYSIZE, d3d10umddi/CalcPrivateQuerySize, UserModeDisplayDriverDx10_Functions_79c9e2a9-e27e-4bd8-bc45-20dd14f0627a.xml
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
-	CalcPrivateQuerySize
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_CALCPRIVATEQUERYSIZE callback


## -description


The <b>CalcPrivateQuerySize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a query.


## -prototype


````
PFND3D10DDI_CALCPRIVATEQUERYSIZE CalcPrivateQuerySize;

SIZE_T APIENTRY CalcPrivateQuerySize(
  _In_       D3D10DDI_HDEVICE        hDevice,
  _In_ const D3D10DDIARG_CREATEQUERY *pCreateQuery
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pCreateQuery [in]

 A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createquery.md">D3D10DDIARG_CREATEQUERY</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region. 


## -returns



<b>CalcPrivateQuerySize</b> returns the size of the memory region that the driver requires for creating a query.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createquery.md">D3D10DDIARG_CREATEQUERY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_CALCPRIVATEQUERYSIZE callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

