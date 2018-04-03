---
UID: NC:dispmprt.DXGKDDI_MIRACAST_CREATE_CONTEXT
title: DXGKDDI_MIRACAST_CREATE_CONTEXT
author: windows-driver-content
description: Creates a kernel-mode context for a Miracast device.
old-location: display\dxgkddimiracastcreatecontext.htm
old-project: display
ms.assetid: BFF952CE-AA0F-4622-BBFC-946A45859FB7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKDDI_MIRACAST_CREATE_CONTEXT, DxgkDdiMiracastCreateContext, DxgkDdiMiracastCreateContext callback function [Display Devices], display.dxgkddimiracastcreatecontext, dispmprt/DxgkDdiMiracastCreateContext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Dispmprt.h
api_name:
-	DxgkDdiMiracastCreateContext
product:
- Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKDDI_MIRACAST_CREATE_CONTEXT callback


## -description


Creates a kernel-mode context for a Miracast device.


## -parameters




### -param DriverContext [in]

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param *MiracastCallbacks [in]

A pointer to an operating system-provided buffer that holds a <a href="https://msdn.microsoft.com/library/windows/hardware/dn344648">DXGK_MIRACAST_DISPLAY_CALLBACKS</a> structure that has pointers to callback functions that the driver can call.


### -param *MiracastContext [out]

A pointer to an operating system-provided buffer that holds the address of the context that the driver allocated for this Miracast device instance.


### -param *TargetId [out]

A pointer to an operating system-provided buffer that holds the  ID of the VidPN target that the Miracast device is connected to. The driver should report this target as type <b>D3DKMDT_VOT_MIRACAST</b> when the operating system calls the <a href="https://msdn.microsoft.com/eb1a0df0-6239-4d82-8477-7dd015f80b6e">DxgkDdiQueryChildRelations</a> function during device initialization.


## -returns



Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes that are defined in Ntstatus.h, including:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_RESOURCE_IN_USE</b></dt>
</dl>
</td>
<td width="60%">
The hardware resources needed to support a Miracast connected session aren't currently available.

</td>
</tr>
</table>
 




## -remarks



When this function is called, the display miniport driver should prepare all kernel-mode resources that it needs to support a Miracast connected session.

<h3><a id="Synchronization"></a><a id="synchronization"></a><a id="SYNCHRONIZATION"></a>Synchronization</h3>
The operating system groups the <i>DxgkDdiMiracastCreateContext</i>, <a href="https://msdn.microsoft.com/2DEEB379-C9E8-45E4-920D-D94F8C27A4EF">DxgkDdiMiracastDestroyContext</a>, and <a href="https://msdn.microsoft.com/83E817C3-A30D-4597-A490-C4FB93A78FCE">DxgkDdiMiracastIoControl</a> functions as a <i>Miracast</i> class. The operating system guarantees that these functions follow the second-level synchronization mode as defined in <a href="https://msdn.microsoft.com/2b7c1eae-6527-469e-a2fa-74d2a1246bd3">Threading and Synchronization Second Level</a>. These functions can be called when other level 0, 1, or other classes of level 2 functions are being called on another thread context. However, only one of these level 2 Miracast-class functions can be called at a time.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn344648">DXGK_MIRACAST_DISPLAY_CALLBACKS</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>



<a href="https://msdn.microsoft.com/eb1a0df0-6239-4d82-8477-7dd015f80b6e">DxgkDdiQueryChildRelations</a>
 

 

