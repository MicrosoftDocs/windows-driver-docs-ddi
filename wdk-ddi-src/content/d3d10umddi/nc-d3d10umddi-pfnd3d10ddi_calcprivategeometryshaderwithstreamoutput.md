---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATEGEOMETRYSHADERWITHSTREAMOUTPUT
title: PFND3D10DDI_CALCPRIVATEGEOMETRYSHADERWITHSTREAMOUTPUT
author: windows-driver-content
description: The CalcPrivateGeometryShaderWithStreamOutput function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a geometry shader with stream output.
old-location: display\calcprivategeometryshaderwithstreamoutput.htm
old-project: display
ms.assetid: 3e760b93-e859-4175-a24a-6bf3648db6db
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.calcprivategeometryshaderwithstreamoutput, CalcPrivateGeometryShaderWithStreamOutput callback function [Display Devices], CalcPrivateGeometryShaderWithStreamOutput, PFND3D10DDI_CALCPRIVATEGEOMETRYSHADERWITHSTREAMOUTPUT, PFND3D10DDI_CALCPRIVATEGEOMETRYSHADERWITHSTREAMOUTPUT, d3d10umddi/CalcPrivateGeometryShaderWithStreamOutput, UserModeDisplayDriverDx10_Functions_f35bbbad-dd97-4149-9bb6-75c6ea2b7cdc.xml
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
-	CalcPrivateGeometryShaderWithStreamOutput
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D10DDI_CALCPRIVATEGEOMETRYSHADERWITHSTREAMOUTPUT callback


## -description


The <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivategeometryshaderwithstreamoutput.md">CalcPrivateGeometryShaderWithStreamOutput</a> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a geometry shader with stream output.


## -prototype


````
PFND3D10DDI_CALCPRIVATEGEOMETRYSHADERWITHSTREAMOUTPUT CalcPrivateGeometryShaderWithStreamOutput;

SIZE_T APIENTRY CalcPrivateGeometryShaderWithStreamOutput(
  _In_       D3D10DDI_HDEVICE                                 hDevice,
  _In_ const D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT *pCreateGeometryShaderWithStreamOutput,
  _In_ const D3D10DDIARG_STAGE_IO_SIGNATURES                  *pSignatures
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE



### -param *






#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pCreateGeometryShaderWithStreamOutput [in]


      A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_creategeometryshaderwithstreamoutput.md">D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region. 
     


#### - pSignatures [in]

 A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_stage_io_signatures.md">D3D10DDIARG_STAGE_IO_SIGNATURES</a> structure that makes up the shader's signature.


## -returns



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivategeometryshaderwithstreamoutput.md">CalcPrivateGeometryShaderWithStreamOutput</a> returns the size of the memory region that the driver requires for creating a geometry shader with stream output.



## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_stage_io_signatures.md">D3D10DDIARG_STAGE_IO_SIGNATURES</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_creategeometryshaderwithstreamoutput.md">D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_CALCPRIVATEGEOMETRYSHADERWITHSTREAMOUTPUT callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

