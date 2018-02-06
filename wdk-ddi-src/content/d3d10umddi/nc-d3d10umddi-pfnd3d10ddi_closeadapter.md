---
UID: NC:d3d10umddi.PFND3D10DDI_CLOSEADAPTER
title: PFND3D10DDI_CLOSEADAPTER
author: windows-driver-content
description: The CloseAdapter(D3D10) function releases resources for a graphics adapter object.
old-location: display\closeadapter_d3d10_.htm
old-project: display
ms.assetid: bc7ccd91-becc-4596-a56a-562cfe9a18b9
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.closeadapter_d3d10_, CloseAdapter callback function [Display Devices], CloseAdapter, PFND3D10DDI_CLOSEADAPTER, PFND3D10DDI_CLOSEADAPTER, d3d10umddi/CloseAdapter, UserModeDisplayDriverDx10_Functions_0adac9d0-3334-4bee-86ef-4e1450b1feb0.xml
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
-	CloseAdapter
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_CLOSEADAPTER callback


## -description


The <b>CloseAdapter(D3D10)</b> function releases resources for a graphics adapter object.


## -prototype


````
PFND3D10DDI_CLOSEADAPTER CloseAdapter;

HRESULT APIENTRY CloseAdapter(
  _In_ D3D10DDI_HADAPTER hAdapter
)
{ ... }
````


## -parameters




### -param D3D10DDI_HADAPTER






#### - hAdapter [in]

 A handle to the graphics adapter object that was created with the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_openadapter.md">OpenAdapter10</a> function.


## -returns


<b>CloseAdapter(D3D10)</b> returns S_OK if the operation succeeds. Otherwise, this function returns an appropriate error result. 



## -remarks


The user-mode display driver's <b>CloseAdapter(D3D10)</b> function should free all of the resources that the driver allocated for the graphics adapter object.

Before <b>CloseAdapter(D3D10)</b> closes the graphics adapter object, all of the display devices that were created by using the graphics adapter object in calls to the user-mode display driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function will be destroyed in calls to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroydevice.md">DestroyDevice(D3D10)</a> function.



## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_adapterfuncs.md">D3D10DDI_ADAPTERFUNCS</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_openadapter.md">OpenAdapter10</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroydevice.md">DestroyDevice(D3D10)</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_CLOSEADAPTER callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

