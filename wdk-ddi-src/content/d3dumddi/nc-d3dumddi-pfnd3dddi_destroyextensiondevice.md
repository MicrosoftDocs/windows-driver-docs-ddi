---
UID: NC:d3dumddi.PFND3DDDI_DESTROYEXTENSIONDEVICE
title: PFND3DDDI_DESTROYEXTENSIONDEVICE
author: windows-driver-content
description: The DestroyExtensionDevice function releases resources for a Microsoft DirectX Video Acceleration (VA) extension device.
old-location: display\destroyextensiondevice.htm
old-project: display
ms.assetid: 8c4bcab3-b903-4f39-aab0-7efb3b18d068
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DestroyExtensionDevice, DestroyExtensionDevice callback function [Display Devices], PFND3DDDI_DESTROYEXTENSIONDEVICE, UserModeDisplayDriver_Functions_6d9ce1e0-efda-4633-83fb-fa6a5aa5f37b.xml, d3dumddi/DestroyExtensionDevice, display.destroyextensiondevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	DestroyExtensionDevice
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_DESTROYEXTENSIONDEVICE callback


## -description


The <b>DestroyExtensionDevice</b> function releases resources for a Microsoft DirectX Video Acceleration (VA) extension device.


## -prototype


````
PFND3DDDI_DESTROYEXTENSIONDEVICE DestroyExtensionDevice;

__checkReturn HRESULT APIENTRY DestroyExtensionDevice(
  _In_ HANDLE hDevice,
  _In_ HANDLE hExtension
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param hExtension [in]

 A handle to the DirectX VA extension device that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createextensiondevice.md">CreateExtensionDevice</a> function created.


## -returns



<b>DestroyExtensionDevice</b> should return S_OK or an appropriate error result if it cannot successfully release resources for the DirectX VA extension device.




## -remarks



The <b>DestroyExtensionDevice</b> function notifies the driver to destroy the handle to the DirectX VA extension device that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createextensiondevice.md">CreateExtensionDevice</a> function previously created. The driver can then release resources that are associated with the DirectX VA extension device handle.




## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createextensiondevice.md">CreateExtensionDevice</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DESTROYEXTENSIONDEVICE callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

