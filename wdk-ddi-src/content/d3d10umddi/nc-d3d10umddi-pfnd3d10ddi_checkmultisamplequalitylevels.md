---
UID: NC:d3d10umddi.PFND3D10DDI_CHECKMULTISAMPLEQUALITYLEVELS
title: PFND3D10DDI_CHECKMULTISAMPLEQUALITYLEVELS
author: windows-driver-content
description: The CheckMultisampleQualityLevels function retrieves the number of quality levels that the device supports for the specified number of samples.
old-location: display\checkmultisamplequalitylevels.htm
old-project: display
ms.assetid: 2b6a0ab8-f197-48c3-baf2-305b77b7e8b5
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: CheckMultisampleQualityLevels, CheckMultisampleQualityLevels callback function [Display Devices], PFND3D10DDI_CHECKMULTISAMPLEQUALITYLEVELS, UserModeDisplayDriverDx10_Functions_d19bc4c0-49ba-4e1c-b19e-667905ceb391.xml, d3d10umddi/CheckMultisampleQualityLevels, display.checkmultisamplequalitylevels
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
-	CheckMultisampleQualityLevels
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_CHECKMULTISAMPLEQUALITYLEVELS callback


## -description


The <b>CheckMultisampleQualityLevels</b> function retrieves the number of quality levels that the device supports for the specified number of samples. 


## -prototype


````
PFND3D10DDI_CHECKMULTISAMPLEQUALITYLEVELS CheckMultisampleQualityLevels;

VOID APIENTRY CheckMultisampleQualityLevels(
  _In_  D3D10DDI_HDEVICE hDevice,
  _In_  DXGI_FORMAT      Format,
  _In_  UINT             SampleCount,
  _Out_ UINT             *pNumQualityLevels
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param DXGI_FORMAT


### -param UINT


### -param *








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - Format [in]

 A DXGI_FORMAT-typed value that indicates the render-target format that the check is performed for. 


#### - SampleCount [in]

 The number of samples to retrieve the quality levels for. 


#### - pNumQualityLevels [out]

A pointer to a variable that receives the number of quality levels that the device supports for the specified number of samples. 


## -returns



None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. The driver can set E_INVALIDARG if the format in the <i>Format</i> parameter does not exist or the <i>pNumQualityLevels</i> parameter is <b>NULL</b>.




## -remarks



If the device does not support multiple sampling with the number of samples that is specified in the <i>SampleCount</i> parameter, the user-mode display driver should return 0 in the variable that the <i>pNumQualityLevels</i> parameter points to.

When the driver returns 1 or more in the variable that <i>pNumQualityLevels</i> points to, the driver indicates the number of device-specific sampling variations that are available with the given sample count. For example, if the driver returns 3, quality levels 0, 1, and 2 can be used to create resources with the given sample count. The device manufacturer defines these quality levels, which the Microsoft Direct3D runtime cannot query. However, different quality levels at a fixed sample count might refer to different spatial layouts of the sample locations or different methods of resolving.

If the driver receives 1 in <i>SampleCount</i>, the driver always returns 1 in the variable that <i>pNumQualityLevels</i> points to.

If the driver receives 0 or greater than 32 in <i>SampleCount</i>, the driver always returns 0 in the variable that <i>pNumQualityLevels</i> points to. 




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_CHECKMULTISAMPLEQUALITYLEVELS callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

