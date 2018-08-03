---
UID: NC:d3d10umddi.PFND3D11_1DDI_FLUSH
title: PFND3D11_1DDI_FLUSH
author: windows-driver-content
description: Submits outstanding hardware commands that are in the hardware command buffer to the display miniport driver. Implemented by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\flush_d3d11_1_.htm
tech.root: display
ms.assetid: 6f4bda19-2d51-4058-ba68-cbb5deb44a54
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: Flush(D3D11_1), Flush(D3D11_1) callback function [Display Devices], PFND3D11_1DDI_FLUSH, PFND3D11_1DDI_FLUSH callback, d3d10umddi/Flush(D3D11_1), display.flush_d3d11_1_
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
-	d3d10umddi.h
api_name:
-	Flush(D3D11_1)
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3D11_1DDI_FLUSH callback function


## -description


Submits outstanding hardware commands that are in the hardware command buffer to the display miniport driver. Implemented by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.


## -parameters




### -param Arg1


### -param FlushFlags [in]

 A value from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451049">D3D11_1_DDI_FLUSH_FLAGS</a> enumeration that indicates whether the driver should  continue to submit command buffers if there have been no new commands.


#### - hDevice [in]

 A handle to the display device (graphics context).


## -returns



Returns <b>TRUE</b> if the hardware commands were successfully flushed. Otherwise returns <b>FALSE</b>.




## -remarks



After the <i>Flush(D3D11_1)</i> function completes, all previously issued commands no longer depend on actions that occur within the application's user-mode context. In addition, applications can safely suspend themselves without blocking rendering until the kernel restarts them (such as, when an asynchronous query is used).

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>Flush(D3D11_1)</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541873">D3D10_1DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451049">D3D11_1_DDI_FLUSH_FLAGS</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

