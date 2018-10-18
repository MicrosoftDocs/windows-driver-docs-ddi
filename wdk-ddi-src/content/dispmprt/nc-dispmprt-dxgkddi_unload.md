---
UID: NC:dispmprt.DXGKDDI_UNLOAD
title: DXGKDDI_UNLOAD
author: windows-driver-content
description: The DxgkDdiUnload function frees any resources allocated during execution of the display miniport driver's DriverEntry function.
old-location: display\dxgkddiunload.htm
tech.root: display
ms.assetid: 336fa87a-6c3e-4337-90d9-b0ebeb355e68
ms.date: 5/10/2018
ms.keywords: DXGKDDI_UNLOAD, DXGKDDI_UNLOAD callback, DmFunctions_b7f60489-c7e7-4bd1-bf17-ff193bc7d614.xml, DxgkDdiUnload, DxgkDdiUnload callback function [Display Devices], display.dxgkddiunload, dispmprt/DxgkDdiUnload
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Dispmprt.h
api_name:
-	DxgkDdiUnload
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_UNLOAD callback function


## -description


The <i>DxgkDdiUnload</i> function frees any resources allocated during execution of the display miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> function.


## -parameters












## -returns



This callback function does not return a value.




## -remarks



Typically, there will be nothing to do in <i>DxgkDdiUnload</i>.

<i>DxgkDdiUnload</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556157">DriverEntry of Display Miniport Driver</a>
 

 

