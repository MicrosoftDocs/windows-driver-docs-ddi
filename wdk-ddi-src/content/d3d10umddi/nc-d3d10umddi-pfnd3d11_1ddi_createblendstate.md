---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATEBLENDSTATE
title: PFND3D11_1DDI_CREATEBLENDSTATE
author: windows-driver-content
description: Creates a blend state.
old-location: display\createblendstate_d3d11_1_.htm
old-project: display
ms.assetid: 5956412e-ae35-4960-afc0-a82c6a2aa9f1
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.createblendstate_d3d11_1_, CreateBlendState(D3D11_1) callback function [Display Devices], CreateBlendState(D3D11_1), PFND3D11_1DDI_CREATEBLENDSTATE, PFND3D11_1DDI_CREATEBLENDSTATE, d3d10umddi/CreateBlendState(D3D11_1), display.pfncreateblendstate
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
-	CreateBlendState(D3D11_1)
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_CREATEBLENDSTATE callback


## -description


Creates a blend state.


## -prototype


````
PFND3D11_1DDI_CREATEBLENDSTATE CreateBlendState(D3D11_1);

VOID APIENTRY* CreateBlendState(D3D11_1)(
             D3D10DDI_HDEVICE       hDevice,
  _In_ const D3D11_1_DDI_BLEND_DESC ,
             D3D10DDI_HBLENDSTATE   hBlendState,
             D3D10DDI_HRTBLENDSTATE hRTBlendState
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE



### -param *



### -param D3D10DDI_HBLENDSTATE



### -param D3D10DDI_HRTBLENDSTATE






#### - hDevice

A handle to the display device (graphics context).




#### - [in]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1_ddi_blend_desc.md">D3D11_1_DDI_BLEND_DESC</a> structure that describes the parameters that the user-mode display driver uses to create a blend state.


#### - hBlendState

A handle to the driver's private data for the blend state. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivateblendstatesize.md">CalcPrivateBlendStateSize(D3D11_1)</a> function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its blend state object.


#### - hRTBlendState

A handle to the blend state that the driver should use when it calls back into the Direct3D runtime.


## -returns


The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the Remarks section.



## -remarks


The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device has been removed) in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is incorrect; therefore, the runtime will not call the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyblendstate.md">DestroyBlendState</a> function to destroy the handle that the <i>hBlendState</i> parameter specifies.

The user-mode display driver is not required to create more than 4,096 unique instances of blend-state objects on a device at one time.



## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyblendstate.md">DestroyBlendState</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivateblendstatesize.md">CalcPrivateBlendStateSize(D3D11_1)</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1_ddi_blend_desc.md">D3D11_1_DDI_BLEND_DESC</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_CREATEBLENDSTATE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

