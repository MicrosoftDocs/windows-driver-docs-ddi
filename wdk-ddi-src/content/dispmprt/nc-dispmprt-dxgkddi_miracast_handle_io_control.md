---
UID: NC:dispmprt.DXGKDDI_MIRACAST_HANDLE_IO_CONTROL
title: DXGKDDI_MIRACAST_HANDLE_IO_CONTROL
author: windows-driver-content
description: Called by the operating system to request that the display miniport driver process a synchronous I/O control request in response to a user-mode display driver call to the MiracastIoControl function.
old-location: display\dxgkddimiracastiocontrol.htm
old-project: display
ms.assetid: 83E817C3-A30D-4597-A490-C4FB93A78FCE
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGKDDI_MIRACAST_HANDLE_IO_CONTROL, DXGKDDI_MIRACAST_HANDLE_IO_CONTROL callback, DxgkDdiMiracastIoControl, DxgkDdiMiracastIoControl callback function [Display Devices], display.dxgkddimiracastiocontrol, dispmprt/DxgkDdiMiracastIoControl
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
-	DxgkDdiMiracastIoControl
product: Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_MIRACAST_HANDLE_IO_CONTROL callback function


## -description


Called by the operating system to request that the display miniport driver process a synchronous I/O control request in response to a user-mode display driver call to the <a href="https://msdn.microsoft.com/df63ec18-79e0-40a6-a412-46071eb8a7fe">MiracastIoControl</a> function.


## -parameters




### -param DriverContext [in]

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param MiracastContext [in]

The Miracast device context, supplied by the operating system. This context was provided by the display miniport driver in a call to the <a href="https://msdn.microsoft.com/BFF952CE-AA0F-4622-BBFC-946A45859FB7">DxgkDdiMiracastCreateContext</a> function.


### -param InputBufferSize [in]

Supplied by the operating system as the size, in bytes, of the input buffer pointed to by <i>pInputBuffer</i>. This value originated as the user-mode <a href="https://msdn.microsoft.com/df63ec18-79e0-40a6-a412-46071eb8a7fe">MiracastIoControl</a> function's <i>InputBufferSize</i> parameter.


### -param *pInputBuffer [in]

Supplied by the operating system as a pointer to the input buffer. This value originated as the user-mode <a href="https://msdn.microsoft.com/df63ec18-79e0-40a6-a412-46071eb8a7fe">MiracastIoControl</a> function's <i>InputBufferSize</i> parameter.

<i>InputBufferSize</i> specifies the size of the buffer.


### -param OutputBufferSize


### -param *pOutputBuffer [out]

Supplied by the operating system as a pointer to the output buffer. This value originated as the user-mode <a href="https://msdn.microsoft.com/df63ec18-79e0-40a6-a412-46071eb8a7fe">MiracastIoControl</a> function's <i>pOutputBuffer</i> parameter.

<i>OutBufferSize</i> specifies the size of the buffer.


### -param *BytesReturned [out]

Supplied by the operating system as a pointer to a buffer that holds a <b>ULONG</b>-type value that is the number of bytes that the display miniport driver returned in the buffer pointed to by <i>pOutputBuffer</i>.


#### - OutBufferSize [in]

Supplied by the operating system as the size, in bytes, of the output buffer pointed to by <i>pOutputBuffer</i>.

This value originated as the user-mode <a href="https://msdn.microsoft.com/df63ec18-79e0-40a6-a412-46071eb8a7fe">MiracastIoControl</a> function's <i>OutputBufferSize</i> parameter.


## -returns



Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes that are defined in Ntstatus.h.




## -remarks



The operating system guarantees that a call to <i>DxgkDdiMiracastIoControl</i> occurs in the same process space as the user-mode <a href="https://msdn.microsoft.com/df63ec18-79e0-40a6-a412-46071eb8a7fe">MiracastIoControl</a> request is called in. 

Even though the operating system merely copies the values of the input and output buffer sizes from the respective parameters of <a href="https://msdn.microsoft.com/df63ec18-79e0-40a6-a412-46071eb8a7fe">MiracastIoControl</a>, the display miniport driver is responsible for checking buffer sizes before using the buffers. Also, the driver should perform probing operations within a try/except calling block, using <a href="https://msdn.microsoft.com/library/windows/hardware/ff559876">ProbeForRead</a> and/or <a href="https://msdn.microsoft.com/library/windows/hardware/ff559879">ProbeForWrite</a> functions, to verify any user-mode memory that input buffers point to.

This I/O control operation is processed synchronously with a call to the user-mode <a href="https://msdn.microsoft.com/df63ec18-79e0-40a6-a412-46071eb8a7fe">MiracastIoControl</a> function.

<h3><a id="Synchronization"></a><a id="synchronization"></a><a id="SYNCHRONIZATION"></a>Synchronization</h3>
The operating system groups the <a href="https://msdn.microsoft.com/BFF952CE-AA0F-4622-BBFC-946A45859FB7">DxgkDdiMiracastCreateContext</a>, <a href="https://msdn.microsoft.com/2DEEB379-C9E8-45E4-920D-D94F8C27A4EF">DxgkDdiMiracastDestroyContext</a>, and <i>DxgkDdiMiracastIoControl</i> functions as a <i>Miracast</i> class. 

The threading and synchronization level for this function is set by how the user-mode driver sets the <i>HardwareAccess</i> parameter in a call to the <a href="https://msdn.microsoft.com/df63ec18-79e0-40a6-a412-46071eb8a7fe">MiracastIoControl</a> function:<ul>
<li>If <i>HardwareAccess</i> is <b>FALSE</b>, then the operating system guarantees that <i>DxgkDdiMiracastIoControl</i> follows the second-level synchronization mode as defined in <a href="https://msdn.microsoft.com/2b7c1eae-6527-469e-a2fa-74d2a1246bd3">Threading and Synchronization Second Level</a>. <i>DxgkDdiMiracastIoControl</i> can be called when other level 0, 1, or non-Miracast classes of level 2 functions are being called on another thread context. However, only one of the level 2 Miracast-class functions can be called at a time.</li>
<li>If <i>HardwareAccess</i> is <b>TRUE</b>, then <i>DxgkDdiMiracastIoControl</i> follows the third-level synchronization mode as defined in <a href="https://msdn.microsoft.com/780d37d9-40c6-4737-9042-473810868227">Threading and Synchronization Third Level</a>. Note that the flushing of the GPU will create substantial processing overhead.</li>
</ul>





## -see-also




<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>



<a href="https://msdn.microsoft.com/BFF952CE-AA0F-4622-BBFC-946A45859FB7">DxgkDdiMiracastCreateContext</a>



<a href="https://msdn.microsoft.com/df63ec18-79e0-40a6-a412-46071eb8a7fe">MiracastIoControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559876">ProbeForRead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559879">ProbeForWrite</a>
 

 

