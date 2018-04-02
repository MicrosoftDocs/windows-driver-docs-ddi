---
UID: NS:d3dkmthk._D3DKMT_POLLDISPLAYCHILDREN
title: "_D3DKMT_POLLDISPLAYCHILDREN"
author: windows-driver-content
description: The D3DKMT_POLLDISPLAYCHILDREN structure describes parameters for querying for connectivity status of all child devices of the given display adapter.
old-location: display\d3dkmt_polldisplaychildren.htm
old-project: display
ms.assetid: 39d62c39-a892-4ccd-aea6-32d102d1891c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMT_POLLDISPLAYCHILDREN, D3DKMT_POLLDISPLAYCHILDREN structure [Display Devices], OpenGL_Structs_08c4958e-cea3-4912-8944-98acb726d798.xml, _D3DKMT_POLLDISPLAYCHILDREN, d3dkmthk/D3DKMT_POLLDISPLAYCHILDREN, display.d3dkmt_polldisplaychildren
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
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
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_POLLDISPLAYCHILDREN
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_POLLDISPLAYCHILDREN
---

# _D3DKMT_POLLDISPLAYCHILDREN structure


## -description


The D3DKMT_POLLDISPLAYCHILDREN structure describes parameters for querying for connectivity status of all child devices of the given display adapter.


## -struct-fields




### -field hAdapter

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle to the graphics adapter to query for connectivity status of child devices.


### -field NonDestructiveOnly

[in] A UINT value that specifies whether the call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547077">D3DKMTPollDisplayChildren</a> function should be only nondestructive. A nonzero value indicates only a nondestructive call; a zero value indicates the call can be destructive (that is, the call can cause visual artifacts on the screen). 


### -field SynchronousPolling

Supported beginning with Windows 7 operating system.

[in] A UINT value that specifies whether the connectivity status of all child devices is reported within 1 second of the call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547077">D3DKMTPollDisplayChildren</a>. If set to a nonzero value, connectivity status is reported within 1 second. Otherwise, there is no time limit on when the display miniport can complete and report the polling.

If the display miniport driver needs to poll child devices after receiving notice of an ACPI event, the runtime should set <b>SynchronousPolling</b> to a nonzero value.


### -field DisableModeReset

Supported beginning with Windows 7 operating system.

[in] A UINT value that specifies whether any reactions of the display miniport driver to discoveries of new child devices are disabled during the polling interval. If set to a nonzero value, such reactions of the driver are disabled during the polling interval. In this case, set the <b>SynchronousPolling</b>parameter when setting <b>DisableModeReset</b>. Otherwise, normal reactions of the driver to discoveries of new child devices are allowed.


### -field PollAllAdapters

Supported beginning with Windows 7 operating system.

[in] A UINT value that specifies whether all child devices are polled. If set to a nonzero value, all child devices are polled. Otherwise, only the child devices that are on the specified adapter are discovered in the polling.


### -field PollInterruptible

Supported beginning with Windows 7 operating system.

[in] A UINT value that specifies whether child devices that are aware of hot-plug detection (HPD) are polled. If set to a nonzero value, HPD-aware child devices are polled. Otherwise, HPD-aware child devices might not be discovered in the polling.

HPD-aware devices are those for which, in a call to <a href="https://msdn.microsoft.com/eb1a0df0-6239-4d82-8477-7dd015f80b6e">DxgkDdiQueryChildRelations</a>, the <b>ChildRelations</b>.<b>ChildCapabilities</b>.<b>HpdAwareness</b> member has a value not equal to HpdAwarenessUninitialized or HpdAwarenessNone.

For more information on HPD-aware devices, see <a href="https://msdn.microsoft.com/170d2d5d-fd46-431d-9672-61fa048f7dd2">Monitor Hot Plug Detection</a>.


### -field Reserved

Supported beginning with Windows 7 operating system.

[in] This member is reserved and should be set to zero. Setting this member is equivalent to setting the remaining 26 bits (0xFFFFFFC0) of a 32-bit value to zeros.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547077">D3DKMTPollDisplayChildren</a>



<a href="https://msdn.microsoft.com/eb1a0df0-6239-4d82-8477-7dd015f80b6e">DxgkDdiQueryChildRelations</a>
 

 

