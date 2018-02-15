---
UID: NC:d3d10umddi.PFND3D10DDI_SO_SETTARGETS
title: PFND3D10DDI_SO_SETTARGETS
author: windows-driver-content
description: The SoSetTargets function sets stream output target resources.
old-location: display\sosettargets.htm
old-project: display
ms.assetid: 96f1c439-7323-456e-8c9c-793d8e0973d9
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.sosettargets, SoSetTargets callback function [Display Devices], SoSetTargets, PFND3D10DDI_SO_SETTARGETS, PFND3D10DDI_SO_SETTARGETS, d3d10umddi/SoSetTargets, UserModeDisplayDriverDx10_Functions_02cc8776-273f-4442-93da-34c2df9746ee.xml
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
-	SoSetTargets
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D10DDI_SO_SETTARGETS callback


## -description


The <i>SoSetTargets</i> function sets stream output target resources.


## -prototype


````
PFND3D10DDI_SO_SETTARGETS SoSetTargets;

VOID APIENTRY SoSetTargets(
  _In_       D3D10DDI_HDEVICE   hDevice,
  _In_       UINT               SOTargets,
  _In_       UINT               ClearTargets,
  _In_ const D3D10DDI_HRESOURCE *phResource,
  _In_ const UINT               *pOffsets
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param NumBuffers


### -param ClearTargets [in]

 The number of handles to stream output target resources that represents the difference between the previous number of stream output target resources (before the Microsoft Direct3D runtime calls <i>SoSetTargets</i>) and the new number of stream output target resources.

Note that the number that i<i>ClearTargets</i> specifies is only an optimization aid because the user-mode display driver could calculate this number. 


### -param *








#### - SOTargets [in]

 The number of elements in the array that <i>phResource</i> specifies. 


#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pOffsets [in]

 An array of offsets, in bytes, into the stream output target resources in the array that <i>phResource</i> specifies. 


#### - phResource [in]

 An array of handles to the stream output target resources to set. Note that some handle values can be <b>NULL</b>. 


## -returns



None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The range of stream output target resources between the number that the <i>SOTargets</i> parameter specifies and the maximum number of stream output target resources that are allowed is required to contain all <b>NULL</b> or unbound values. The number that the <i>ClearTargets</i> parameter specifies informs the driver about how many bind points the driver must clear out for the current operation. If the previous call to <i>SoSetTargets</i> passed a value of 2 in <i>SOTargets</i>and the current call to <i>SoSetTargets</i> passes a value of 4 in <i>SOTargets</i>, the current call to <i>SoSetTargets</i> also passes a value of 0 in the <i>ClearTargets</i> parameter. If the next successive call to <i>SoSetTargets</i> passes a value of 1 in <i>SOTargets</i>, the successive call also passes a value of 3 (4 - 1) in <i>ClearTargets</i>.

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Microsoft Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>SOTargets</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_SO_SETTARGETS callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

