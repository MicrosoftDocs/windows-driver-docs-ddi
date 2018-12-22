---
UID: NC:d3dkmddi.DXGKCB_HARDWARECONTENTPROTECTIONTEARDOWN
title: DXGKCB_HARDWARECONTENTPROTECTIONTEARDOWN
description: DxgkCbHardwareContentProtectionTeardown is used to indicate when a hardware content protection event occurs.
old-location: display\dxgkcbhardwarecontentprotectionteardown.htm
ms.assetid: 7B12B9AD-2288-4CE0-A4D8-F1C96150CE45
ms.date: 05/10/2018
ms.keywords: DXGKCB_HARDWARECONTENTPROTECTIONTEARDOWN, DXGKCB_HARDWARECONTENTPROTECTIONTEARDOWN callback, DxgkCbHardwareContentProtectionTeardown, DxgkCbHardwareContentProtectionTeardown callback function [Display Devices], d3dkmddi/DxgkCbHardwareContentProtectionTeardown, display.dxgkcbhardwarecontentprotectionteardown
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	d3dkmddi.h
api_name:
-	DxgkCbHardwareContentProtectionTeardown
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKCB_HARDWARECONTENTPROTECTIONTEARDOWN callback function


## -description


<b>DxgkCbHardwareContentProtectionTeardown</b> is used to indicate when a hardware content protection event occurs.


## -parameters




### -param hAdapter

A handle to the graphics adapter where the tear-down event is occurring.


### -param Flags

Additional flags defined by <a href="https://msdn.microsoft.com/library/windows/hardware/dn906828">DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS</a> enumeration.


## -returns



This callback function does not return a value.




## -remarks



The kernel mode driver should always call this callback before and after a hardware content protection tear-down event occurs.



The driver can call this callback at either passive level or at dispatch level.





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906828">DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS</a>
 

 

