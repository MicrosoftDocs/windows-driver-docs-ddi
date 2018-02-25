---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATEVIDEOPROCESSORENUM
title: PFND3D11_1DDI_CREATEVIDEOPROCESSORENUM
author: windows-driver-content
description: Creates an enumeration object for the video processor capabilities of the driver.
old-location: display\createvideoprocessorenum.htm
old-project: display
ms.assetid: 38c27502-7e8a-45a1-8a7c-315300502480
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: CreateVideoProcessorEnum, CreateVideoProcessorEnum callback function [Display Devices], PFND3D11_1DDI_CREATEVIDEOPROCESSORENUM, d3d10umddi/CreateVideoProcessorEnum, display.createvideoprocessorenum
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	D3d10umddi.h
apiname:
-	CreateVideoProcessorEnum
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_CREATEVIDEOPROCESSORENUM callback


## -description


Creates an enumeration object for the video processor capabilities of the driver.


## -prototype


````
PFND3D11_1DDI_CREATEVIDEOPROCESSORENUM CreateVideoProcessorEnum;

HRESULT APIENTRY* CreateVideoProcessorEnum(
  _In_       D3D10DDI_HDEVICE                       hDevice,
  _In_ const D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM *pCreateData,
  _In_       D3D11_1DDI_HVIDEOPROCESSORENUM         hVideoProcessorEnum,
  _In_       D3D11_1DDI_HRTVIDEOPROCESSORENUM       hRTVideoProcessorEnum
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *


### -param D3D11_1DDI_HVIDEOPROCESSORENUM


### -param D3D11_1DDI_HRTVIDEOPROCESSORENUM








#### - hDevice [in]

A handle to the display device (graphics context).




#### - pCreateData [in]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createvideoprocessorenum.md">D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM</a> structure. This structure specifies the attributes of the video processor enumeration object to be created.


#### - hVideoProcessorEnum [in]

A handle to the driver's private data for the video processor enumeration object. For more information, see the Remarks section.


#### - hRTVideoProcessorEnum [in]

A handle to the video processor enumeration object that the driver should use when it calls back into the Direct3D runtime.


## -returns



<b>CreateVideoProcessorEnum</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The video processor enumeration object was created successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

        Memory was not available to complete the operation.

</td>
</tr>
</table>
 




## -remarks



The Direct3D runtime calls <i>CreateVideoProcessorEnum</i> after it has called the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessorsize.md">CalcPrivateVideoProcessorEnumSize </a>   to determine the size in bytes for the private data that the driver requires for the video processor enumeration object. The runtime allocates the memory for this private data for the driver. The driver uses this memory to store private data that is related to the video processor enumeration object.

When the runtime  calls <i>CreateVideoProcessorEnum</i>, it passes the handle to the private data memory in the <i>hVideoProcessorEnum</i> parameter. This handle is actually a pointer to the memory. 




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessorsize.md">CalcPrivateVideoProcessorEnumSize </a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createvideoprocessorenum.md">D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_CREATEVIDEOPROCESSORENUM callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

