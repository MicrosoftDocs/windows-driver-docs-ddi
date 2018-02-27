---
UID: NC:d3d10umddi.PFND3D11DDI_RELOCATEDEVICEFUNCS
title: PFND3D11DDI_RELOCATEDEVICEFUNCS
author: windows-driver-content
description: The RelocateDeviceFuncs(D3D11) function notifies the user-mode display driver about the new location of the driver function table.
old-location: display\relocatedevicefuncs_d3d11_.htm
old-project: display
ms.assetid: 1d56c71f-0108-4088-a5e0-3b41b781f361
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PFND3D11DDI_RELOCATEDEVICEFUNCS, RelocateDeviceFuncs, RelocateDeviceFuncs callback function [Display Devices], UserModeDisplayDriverDx11_Functions_ef0af03c-0ab5-4ea2-a568-410d1f68c183.xml, d3d10umddi/RelocateDeviceFuncs, display.relocatedevicefuncs_d3d11_
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: RelocateDeviceFuncs(D3D11) is supported beginning with the Windows 7 operating system.
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
-	RelocateDeviceFuncs
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11DDI_RELOCATEDEVICEFUNCS callback


## -description


The <i>RelocateDeviceFuncs(D3D11)</i> function notifies the user-mode display driver about the new location of the driver function table. 


## -prototype


````
PFND3D11DDI_RELOCATEDEVICEFUNCS RelocateDeviceFuncs;

VOID APIENTRY RelocateDeviceFuncs(
  _In_ D3D10DDI_HDEVICE            hDevice,
  _In_ struct D3D11DDI_DEVICEFUNCS *pDeviceFunctions
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pDeviceFunctions [in]

 A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a> structure that contains pointers to the functions of the user-mode display driver. 


## -returns



None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. 




## -remarks



A user-mode display driver can use the <i>RelocateDeviceFuncs(D3D11)</i> function to replace function pointers in the driver function table. 




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11DDI_RELOCATEDEVICEFUNCS callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

