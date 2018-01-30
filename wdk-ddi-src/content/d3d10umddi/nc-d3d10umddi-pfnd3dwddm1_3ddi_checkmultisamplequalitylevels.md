---
UID: NC:d3d10umddi.PFND3DWDDM1_3DDI_CHECKMULTISAMPLEQUALITYLEVELS
title: PFND3DWDDM1_3DDI_CHECKMULTISAMPLEQUALITYLEVELS
author: windows-driver-content
description: Retrieves the number of quality levels that the device supports for the specified number of samples. Supported.
old-location: display\checkmultisamplequalitylevels_d3d11_2_.htm
old-project: display
ms.assetid: A3AD5F2F-4FB9-407C-A436-A0B5F96002D7
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.checkmultisamplequalitylevels_d3d11_2_, CheckMultisampleQualityLevels callback function [Display Devices], CheckMultisampleQualityLevels, PFND3DWDDM1_3DDI_CHECKMULTISAMPLEQUALITYLEVELS, PFND3DWDDM1_3DDI_CHECKMULTISAMPLEQUALITYLEVELS, d3d10umddi/CheckMultisampleQualityLevels
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,WDDM 1.3
req.target-min-winversvr: Windows Server 2012 R2
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
-	CheckMultisampleQualityLevels
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3DWDDM1_3DDI_CHECKMULTISAMPLEQUALITYLEVELS callback


## -description


 Retrieves the number of quality levels that the device supports for the specified number of samples. Supported 


## -prototype


````
PFND3DWDDM1_3DDI_CHECKMULTISAMPLEQUALITYLEVELS CheckMultisampleQualityLevels;

VOID APIENTRY* CheckMultisampleQualityLevels(
        D3D10DDI_HDEVICE hDevice,
        DXGI_FORMAT      Format,
        UINT             SampleCount,
        UINT             Flags,
  _Out_ UINT             *pNumQualityLevels
)
{ ... }
````


## -parameters




### -param hDevice

A handle to the display device (graphics context).


### -param Format

A value of type <a href="https://msdn.microsoft.com/dce61bc4-4ed5-4e64-84e8-6db88025e5c2">DXGI_FORMAT</a> that indicates the render-target format that the check is performed for.


### -param SampleCount

The number of samples to retrieve the quality levels for. 


### -param Flags

A combination of <a href="..\d3d10umddi\ne-d3d10umddi-d3dwddm1_3ddi_check_multisample_quality_levels_flag.md">D3DWDDM1_3DDI_CHECK_MULTISAMPLE_QUALITY_LEVELS_FLAG</a> values that are combined by using a bitwise <b>OR</b> operation.


### -param *pNumQualityLevels






#### - pNumQualityLevels [out]

A pointer to a variable that receives the number of quality levels that the device supports for the specified number of samples.


## -returns


None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. The driver can set <b>E_INVALIDARG</b> if the format in the <i>Format</i> parameter does not exist or the <i>pNumQualityLevels</i> parameter is <b>NULL</b>.



## -remarks


If the device does not support multiple sampling with the number of samples that is specified in the <i>SampleCount</i> parameter, the user-mode display driver should return zero in the variable that the <i>pNumQualityLevels</i> parameter points to.

When the driver returns 1 or more in the variable that <i>pNumQualityLevels</i> points to, the driver indicates the number of device-specific sampling variations that are available with the given sample count. For example, if the driver returns 3, quality levels 0, 1, and 2 can be used to create resources with the given sample count. The device manufacturer defines these quality levels, which the Microsoft Direct3D runtime cannot query. However, different quality levels at a fixed sample count might refer to different spatial layouts of the sample locations or different methods of resolving.

If the driver receives 1 in <i>SampleCount</i>, the driver always returns 1 in the variable that <i>pNumQualityLevels</i> points to.

If the driver receives 0 or greater than 32 in <i>SampleCount</i>, the driver always returns 0 in the variable that <i>pNumQualityLevels</i> points to. 



## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_checkmultisamplequalitylevels.md">CheckMultisampleQualityLevels</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>

<a href="..\d3d10umddi\ne-d3d10umddi-d3dwddm1_3ddi_check_multisample_quality_levels_flag.md">D3DWDDM1_3DDI_CHECK_MULTISAMPLE_QUALITY_LEVELS_FLAG</a>

<a href="https://msdn.microsoft.com/dce61bc4-4ed5-4e64-84e8-6db88025e5c2">DXGI_FORMAT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DWDDM1_3DDI_CHECKMULTISAMPLEQUALITYLEVELS callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

