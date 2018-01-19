---
UID: NC:d3d10umddi.PFND3D10_1DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE
title: PFND3D10_1DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE
author: windows-driver-content
description: The CalcPrivateShaderResourceViewSize(D3D10_1) function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader resource view.
old-location: display\calcprivateshaderresourceviewsize_d3d10_1_.htm
old-project: display
ms.assetid: 310adb3e-1af4-430e-ba50-bd145ffda361
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _SETRESULT_INFO, *PSETRESULT_INFO, SETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CalcPrivateShaderResourceViewSize(D3D10_1) is supported on Windows Vista with Service Pack 1 (SP1) and later versions and Windows Server 2008 and later versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CalcPrivateShaderResourceViewSize_d3d10_1_
req.alt-loc: d3d10umddi.h
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
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
---

# PFND3D10_1DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE callback



## -description
The <b>CalcPrivateShaderResourceViewSize(D3D10_1)</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader resource view.



## -prototype

````
PFND3D10_1DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE CalcPrivateShaderResourceViewSize_d3d10_1_;

SIZE_T APIENTRY CalcPrivateShaderResourceViewSize_d3d10_1_(
  _In_       D3D10DDI_HDEVICE                       hDevice,
  _In_ const D3D10_1DDIARG_CREATESHADERRESOURCEVIEW *pCreateShaderResourceView
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param pCreateShaderResourceView [in]

 A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10_1ddiarg_createshaderresourceview.md">D3D10_1DDIARG_CREATESHADERRESOURCEVIEW</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region. 


## -returns
<b>CalcPrivateShaderResourceViewSize(D3D10_1)</b> returns the size of the memory region that the driver requires for creating a shader resource view.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_1ddi_devicefuncs.md">D3D10_1DDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_1ddiarg_createshaderresourceview.md">D3D10_1DDIARG_CREATESHADERRESOURCEVIEW</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10_1DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

