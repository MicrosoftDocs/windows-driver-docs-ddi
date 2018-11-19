---
UID: NC:d3dkmddi.DXGKDDI_ESCAPE
title: DXGKDDI_ESCAPE
author: windows-driver-content
description: The DxgkDdiEscape function shares information with the user-mode display driver.
old-location: display\dxgkddiescape.htm
ms.assetid: 79a524cd-dec1-4ea8-a660-d9d9c644e162
ms.date: 05/10/2018
ms.keywords: DXGKDDI_ESCAPE, DXGKDDI_ESCAPE callback, DmFunctions_41056daa-dfeb-4ba3-b453-b8d5dd94e8a3.xml, DxgkDdiEscape, DxgkDdiEscape callback function [Display Devices], d3dkmddi/DxgkDdiEscape, display.dxgkddiescape
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
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
-	d3dkmddi.h
api_name:
-	DxgkDdiEscape
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_ESCAPE callback function


## -description


The <i>DxgkDdiEscape</i> function shares information with the user-mode display driver.


## -parameters




### -param hAdapter [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function.


### -param pEscape [in]

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557588">DXGKARG_ESCAPE</a> structure that contains information about the shared information.

<div class="alert"><b>Note</b>  In order for the <b>DxgkDdiEscape</b> call to be made under the second level, the <b>HardwareAccess</b> flag must be set within the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544541">D3DDDI_ESCAPEFLAGS</a> structure that is a member of <i>DXGKARG_ESCAPE</i>. If this flag is not set, then the call will fail.</div>
<div> </div>

## -returns



<i>DxgkDdiEscape</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|DxgkDdiEscape successfully shared information.|
|STATUS_INVALID_PARAMETER|Parameters that were passed to DxgkDdiEscape contained errors that prevented it from completing.|
|STATUS_NO_MEMORY|DxgkDdiEscape could not allocate memory that was required for it to complete.|
|STATUS_PRIVILEGED_INSTRUCTION|DxgkDdiEscape detected nonprivileged instructions (that is, instructions that access memory beyond the privilege of the current central processing unit [CPU] process).|
|STATUS_ILLEGAL_INSTRUCTION|DxgkDdiEscape detected instructions that graphics hardware could not support.|
|STATUS_GRAPHICS_DRIVER_MISMATCH|The display miniport driver is not compatible with the user-mode display driver that initiated the call to DxgkDdiEscape.|

## -remarks



The DirectX graphics kernel subsystem calls the display miniport driver's <i>DxgkDdiEscape</i> function whenever the user-mode display driver must share information with the display miniport driver in a way that is not supported through other driver communications. 

<i>DxgkDdiEscape</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557588">DXGKARG_ESCAPE</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>



<a href="https://msdn.microsoft.com/66c0347f-2cf3-42fc-8641-47c731e958c9">pfnEscapeCb</a>
 

 

