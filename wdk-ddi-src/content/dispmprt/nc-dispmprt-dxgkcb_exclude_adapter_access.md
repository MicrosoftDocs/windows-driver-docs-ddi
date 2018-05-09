---
UID: NC:dispmprt.DXGKCB_EXCLUDE_ADAPTER_ACCESS
title: DXGKCB_EXCLUDE_ADAPTER_ACCESS
author: windows-driver-content
description: The DxgkCbExcludeAdapterAccess function prevents all access to the display adapter and calls a provided DxgkProtectedCallback callback routine while in this protected state.
old-location: display\dxgkcbexcludeadapteraccess.htm
old-project: display
ms.assetid: e74e79fe-3b36-427e-ae0b-4072a0438c4e
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGKCB_EXCLUDE_ADAPTER_ACCESS, DXGKCB_EXCLUDE_ADAPTER_ACCESS callback, DpFunctions_8ad0a347-3d2f-429c-9b1f-67f000dbfc03.xml, DxgkCbExcludeAdapterAccess, DxgkCbExcludeAdapterAccess callback function [Display Devices], display.dxgkcbexcludeadapteraccess, dispmprt/DxgkCbExcludeAdapterAccess
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	dispmprt.h
api_name:
-	DxgkCbExcludeAdapterAccess
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKCB_EXCLUDE_ADAPTER_ACCESS callback function


## -description


The <b>DxgkCbExcludeAdapterAccess</b> function prevents all access to the display adapter and calls a provided <a href="https://msdn.microsoft.com/7e282ec6-c159-47a4-af14-2b0cb8e34a8e">DxgkProtectedCallback</a> callback routine while in this protected state.


## -parameters




### -param DeviceHandle [in]

A handle that represents a display adapter. The display miniport driver obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure that was passed to <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a>.


### -param Attributes [in]

A value that specifies video memory operations. This parameter can be any combination of the following bit flag values, except that DXGK_EXCLUDE_EVICT_ALL and DXGK_EXCLUDE_CALL_SYNCHRONOUS are mutually exclusive. These values are defined in <i>Dispmprt.h</i>.





#### DXGK_EXCLUDE_EVICT_ALL

All video memory in the adapter is copied to system memory; this is an expensive operation. If the <i>Attributes</i> parameter is not set to this value, access to locked surfaces in system memory is suspended.



#### DXGK_EXCLUDE_CALL_SYNCHRONOUS

Executes the protected <a href="https://msdn.microsoft.com/7e282ec6-c159-47a4-af14-2b0cb8e34a8e">DxgkProtectedCallback</a> driver callback routine in the same thread context as the caller. The caller must be calling from a <a href="https://msdn.microsoft.com/2b7c1eae-6527-469e-a2fa-74d2a1246bd3">second level</a> or <a href="https://msdn.microsoft.com/780d37d9-40c6-4737-9042-473810868227">third level</a> synchronized DDI call. Otherwise the <b>DxgkCbExcludeAdapterAccess</b> function will fail.



#### DXGK_EXCLUDE_BRIDGE_ACCESS

Protects access to the PCI Express (PCIe) root port when the driver needs to access the root port configuration space. Set the <i>Attributes</i> parameter to this value before calling <a href="https://msdn.microsoft.com/118ea0b9-6463-4050-9f33-192a3d42fdce">DxgkCbReadDeviceSpace</a> or <a href="https://msdn.microsoft.com/797d6b0c-91a4-4923-ad40-937cfde50067">DxgkCbWriteDeviceSpace</a> functions with the <i>DataType</i> parameter set to DXGK_WHICHSPACE_BRIDGE.


### -param DxgkProtectedCallback [in]

The callback routine to be called back when all access to the adapter has been halted.


### -param ProtectedCallbackContext [in]

A pointer to the value to pass to the <i>ProtectedCallbackContext</i> parameter of the <a href="https://msdn.microsoft.com/7e282ec6-c159-47a4-af14-2b0cb8e34a8e">DxgkProtectedCallback</a> callback routine.


## -returns



<b>DxgkCbExcludeAdapterAccess</b> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.




## -remarks



Application requests will be blocked until this function returns. While in this protective state, the provided <a href="https://msdn.microsoft.com/7e282ec6-c159-47a4-af14-2b0cb8e34a8e">DxgkProtectedCallback</a> callback routine is called at IRQL = PASSIVE_LEVEL.

<b>DxgkCbExcludeAdapterAccess</b> acquires exclusive adapter access in order to prevent graphics-related I/O operations to the display adapter and all links. This effectively idles the GPU for the entire duration of the call.

This function also prevents all PCI configuration space access to the PCI Express (PCIe) root port if DXGK_EXCLUDE_BRIDGE_ACCESS is specified in the <i>Attributes</i> parameter.

The driver should not block continued execution of the calling thread by waiting for the <a href="https://msdn.microsoft.com/7e282ec6-c159-47a4-af14-2b0cb8e34a8e">DxgkProtectedCallback</a> callback routine to return. For example, the driver could schedule an asynchronous worker thread to handle the callback routine.

An exception to this blocking of application requests occurs when the user-mode display driver has set the <b>UseAlternateVA</b> bit-field flag in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544214">D3DDDICB_LOCKFLAGS</a> structure in a call to the <a href="https://msdn.microsoft.com/69022797-432a-410b-8cbf-e1ef7111e7ea">pfnLockCb</a> function. <b>DxgkCbExcludeAdapterAccess</b> does not block this type of allocation lock, and the CPU can access the display adapter while the protected callback routine is executing.

<div class="alert"><b>Note</b>  If <b>UseAlternateVA</b> has been set in a call to <b>pfnLockCb</b>, the display miniport driver should not call <b>DxgkCbExcludeAdapterAccess</b>.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/7e282ec6-c159-47a4-af14-2b0cb8e34a8e">DxgkProtectedCallback</a>
 

 

