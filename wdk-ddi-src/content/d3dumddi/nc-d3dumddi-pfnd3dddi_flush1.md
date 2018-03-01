---
UID: NC:d3dumddi.PFND3DDDI_FLUSH1
title: PFND3DDDI_FLUSH1
author: windows-driver-content
description: Called by the Microsoft Direct3D runtime to submit outstanding hardware commands that are in the hardware command buffer to the display miniport driver. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.
old-location: display\pfnflush1.htm
old-project: display
ms.assetid: 6BAC104A-85CE-42FC-AE30-969B2FF6AFEF
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PFND3DDDI_FLUSH1, d3dumddi/pfnFlush1, display.pfnflush1, pfnFlush1, pfnFlush1 callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3dumddi.h
api_name:
-	pfnFlush1
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_FLUSH1 callback


## -description


Called by the Microsoft Direct3D runtime to submit outstanding hardware commands that are in the hardware command buffer to the display miniport driver. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.



## -prototype


````
PFND3DDDI_FLUSH1 pfnFlush1;

_Check_return_ HRESULT APIENTRY* pfnFlush1(
  _In_ HANDLE hDevice,
       UINT   FlushFlags
)
{ ... }
````


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).




### -param FlushFlags

A value from the <a href="..\d3dumddi\ne-d3dumddi-d3dddi_flush_flags.md">D3DDDI_FLUSH_FLAGS</a> enumeration that indicates whether the driver should continue to submit command buffers if there have been no new commands.


## -returns



If this routine succeeds, it returns <b>S_OK</b>. Otherwise, it returns an <b>HRESULT</b> error code.




## -see-also

<a href="..\d3dumddi\ne-d3dumddi-d3dddi_flush_flags.md">D3DDDI_FLUSH_FLAGS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_FLUSH1 callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

