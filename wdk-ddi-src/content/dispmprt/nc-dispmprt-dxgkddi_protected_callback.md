---
UID: NC:dispmprt.DXGKDDI_PROTECTED_CALLBACK
title: DXGKDDI_PROTECTED_CALLBACK (dispmprt.h)
description: The DxgkProtectedCallback callback routine is implemented by the display miniport driver and is called by DxgkCbExcludeAdapterAccess during a protected state when all access to the display adapter is prevented.
old-location: display\dxgkprotectedcallback.htm
tech.root: display
ms.assetid: 7e282ec6-c159-47a4-af14-2b0cb8e34a8e
ms.date: 05/10/2018
keywords: ["DXGKDDI_PROTECTED_CALLBACK callback function"]
ms.keywords: DXGKDDI_PROTECTED_CALLBACK, DXGKDDI_PROTECTED_CALLBACK callback, DmFunctions_a4386149-d1c4-45f4-8649-5539783620f4.xml, DxgkProtectedCallback, DxgkProtectedCallback callback function [Display Devices], display.dxgkprotectedcallback, dispmprt/DxgkProtectedCallback
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
targetos: Windows
req.typenames: 
f1_keywords:
 - DXGKDDI_PROTECTED_CALLBACK
 - dispmprt/DXGKDDI_PROTECTED_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DxgkProtectedCallback
---

# DXGKDDI_PROTECTED_CALLBACK callback function


## -description

The <i>DxgkProtectedCallback</i> callback routine is implemented by the display miniport driver and is called by <a href="..\dispmprt\nc-dispmprt-dxgkcb_exclude_adapter_access.md">DxgkCbExcludeAdapterAccess</a> during a protected state when all access to the display adapter is prevented.

## -parameters

### -param MiniportDeviceContext

[in] A handle to a context block associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.

### -param ProtectedCallbackContext 

[in] A pointer to driver-defined information that was specified in a previous call to <a href="..\dispmprt\nc-dispmprt-dxgkcb_exclude_adapter_access.md">DxgkCbExcludeAdapterAccess</a>.

### -param ProtectionStatus 

[in] Status of the display adapter's protected state. If STATUS_SUCCESS, the adapter was successfully protected from access. A failure status code indicates that the adapter is not protected.

## -prototype

```cpp
DXGKDDI_PROTECTED_CALLBACK DxgkProtectedCallback;

VOID DxgkProtectedCallback(
  _In_ const PVOID    MiniportDeviceContext,
  _In_       PVOID    ProtectedCallbackContext,
  _In_       NTSTATUS ProtectionStatus
)
{ ... }
```

## -remarks

<i>DxgkProtectedCallback</i> must be called only when all access to the display adapter has been halted, as indicated by the status parameter <i>ProtectionStatus.</i>

The driver must ensure that following conditions are met during the callback routine:

<ul>
<li>
All interrupts on the device are disabled, and any remaining pending interrupts are handled, including any DPCs that may have been queued on any CPU but not yet serviced.

</li>
<li>
All write-combined memory and any other cache-related states have been flushed.

</li>
<li>
Any ACPI or BIOS/SMI events that occur do not access the hardware.

</li>
<li>
Coherency is achieved between all adapters in a linked-adapter state configuration.

</li>
<li>
The adapter, including its registers and display mode, is maintained in the proper state to handle the DMA buffer that occurs on the return from the <i>DxgkProtectedCallback</i> routine. The driver should not change the visible state or capabilities of any application.

</li>
</ul>

## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkcb_exclude_adapter_access.md">DxgkCbExcludeAdapterAccess</a>

