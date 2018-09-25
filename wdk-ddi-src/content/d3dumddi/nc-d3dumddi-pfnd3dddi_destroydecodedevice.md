---
UID: NC:d3dumddi.PFND3DDDI_DESTROYDECODEDEVICE
title: PFND3DDDI_DESTROYDECODEDEVICE
author: windows-driver-content
description: The DestroyDecodeDevice function releases resources for a Microsoft DirectX Video Acceleration (VA) decode device.
old-location: display\destroydecodedevice.htm
tech.root: display
ms.assetid: 3685e58b-8d67-4b01-a8a0-8a794d653637
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DestroyDecodeDevice, DestroyDecodeDevice callback function [Display Devices], PFND3DDDI_DESTROYDECODEDEVICE, PFND3DDDI_DESTROYDECODEDEVICE callback, UserModeDisplayDriver_Functions_1a057944-edfe-4010-8726-9ac1deef11e6.xml, d3dumddi/DestroyDecodeDevice, display.destroydecodedevice
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
-	DestroyDecodeDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_DESTROYDECODEDEVICE callback function


## -description


The <b>DestroyDecodeDevice</b> function releases resources for a Microsoft DirectX Video Acceleration (VA) decode device.


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param Arg1








#### - hDecodeDevice [in]

 A handle to the DirectX VA decode device that was created by the <a href="https://msdn.microsoft.com/4d9a062a-2fdf-4e55-a335-c03c5d5665ff">CreateDecodeDevice</a> function.


## -returns



<b>DestroyDecodeDevice</b> should return S_OK or an appropriate error result if it cannot successfully release resources for the DirectX VA decode device.




## -remarks



The <b>DestroyDecodeDevice</b> function notifies the driver to destroy the handle to the DirectX VA decode device that the <a href="https://msdn.microsoft.com/4d9a062a-2fdf-4e55-a335-c03c5d5665ff">CreateDecodeDevice</a> function previously created. The driver can then release resources that are associated with the DirectX VA decode device handle.




## -see-also




<a href="https://msdn.microsoft.com/4d9a062a-2fdf-4e55-a335-c03c5d5665ff">CreateDecodeDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 

