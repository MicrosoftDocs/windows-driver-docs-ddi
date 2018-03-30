---
UID: NC:d3d10umddi.PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORENUMSIZE
title: PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORENUMSIZE
author: windows-driver-content
description: Returns the number of bytes that the driver requires to store private data for the video processor enumeration state.
old-location: display\calcprivatevideoprocessorenumsize.htm
old-project: display
ms.assetid: d468c892-6635-40a5-ad52-cbcc86555419
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CalcPrivateVideoProcessorEnumSize, CalcPrivateVideoProcessorEnumSize callback function [Display Devices], PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORENUMSIZE, d3d10umddi/CalcPrivateVideoProcessorEnumSize, display.calcprivatevideoprocessorenumsize
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	CalcPrivateVideoProcessorEnumSize
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_CALCPRIVATEVIDEOPROCESSORENUMSIZE callback


## -description


Returns the number of bytes that the driver requires to store private data for the video processor enumeration state.


## -parameters




### -param Arg1


### -param *








#### - hDevice [in]

A handle to the display device (graphics context).




#### - pProcessorEnum [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406316">D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM</a> structure that describes the video processor enumeration object that was created through the <a href="https://msdn.microsoft.com/38c27502-7e8a-45a1-8a7c-315300502480">CreateVideoProcessorEnum</a> function.


## -returns



The required number of bytes for the video processor enumeration state.




## -remarks



This function is not expected to fail.




## -see-also




<a href="https://msdn.microsoft.com/38c27502-7e8a-45a1-8a7c-315300502480">CreateVideoProcessorEnum</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406316">D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM</a>
 

 

