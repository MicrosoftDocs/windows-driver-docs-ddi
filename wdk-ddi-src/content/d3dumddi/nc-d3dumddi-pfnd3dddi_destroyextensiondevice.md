---
UID: NC:d3dumddi.PFND3DDDI_DESTROYEXTENSIONDEVICE
title: PFND3DDDI_DESTROYEXTENSIONDEVICE
author: windows-driver-content
description: The DestroyExtensionDevice function releases resources for a Microsoft DirectX Video Acceleration (VA) extension device.
old-location: display\destroyextensiondevice.htm
tech.root: display
ms.assetid: 8c4bcab3-b903-4f39-aab0-7efb3b18d068
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DestroyExtensionDevice, DestroyExtensionDevice callback function [Display Devices], PFND3DDDI_DESTROYEXTENSIONDEVICE, PFND3DDDI_DESTROYEXTENSIONDEVICE callback, UserModeDisplayDriver_Functions_6d9ce1e0-efda-4633-83fb-fa6a5aa5f37b.xml, d3dumddi/DestroyExtensionDevice, display.destroyextensiondevice
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_DESTROYEXTENSIONDEVICE callback function


## -description


The <b>DestroyExtensionDevice</b> function releases resources for a Microsoft DirectX Video Acceleration (VA) extension device.


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param hExtension [in]

 A handle to the DirectX VA extension device that the <a href="https://msdn.microsoft.com/7e6dbb70-2e74-4ddb-a504-2c8145af99d9">CreateExtensionDevice</a> function created.


## -returns



<b>DestroyExtensionDevice</b> should return S_OK or an appropriate error result if it cannot successfully release resources for the DirectX VA extension device.




## -remarks



The <b>DestroyExtensionDevice</b> function notifies the driver to destroy the handle to the DirectX VA extension device that the <a href="https://msdn.microsoft.com/7e6dbb70-2e74-4ddb-a504-2c8145af99d9">CreateExtensionDevice</a> function previously created. The driver can then release resources that are associated with the DirectX VA extension device handle.




## -see-also




<a href="https://msdn.microsoft.com/7e6dbb70-2e74-4ddb-a504-2c8145af99d9">CreateExtensionDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 

