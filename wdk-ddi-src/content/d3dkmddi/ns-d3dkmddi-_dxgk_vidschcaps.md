---
UID: NS:d3dkmddi._DXGK_VIDSCHCAPS
title: DXGK_VIDSCHCAPS (d3dkmddi.h)
description: Learn more about the DXGK_VIDSCHCAPS structure.
ms.date: 03/28/2024
keywords: ["DXGK_VIDSCHCAPS structure"]
req.header: d3dkmddi.h
req.construct-type: structure
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
targetos: Windows
tech.root: display
req.typenames: DXGK_VIDSCHCAPS
f1_keywords:
 - _DXGK_VIDSCHCAPS
 - d3dkmddi/_DXGK_VIDSCHCAPS
 - DXGK_VIDSCHCAPS
 - d3dkmddi/DXGK_VIDSCHCAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_VIDSCHCAPS
 - DXGK_VIDSCHCAPS
---

# DXGK_VIDSCHCAPS structure (d3dkmddi.h)



## -description

The **DXGK_VIDSCHCAPS** structure has bit-field flags that identify the GPU's scheduling capabilities that a kernel-mode display miniport driver (KMD) can support.

## -struct-fields

### -field MultiEngineAware

A UINT value that specifies whether the driver supports the creation and destruction of a device context (through the [**DxgkDdiCreateContext**](./nc-d3dkmddi-dxgkddi_createcontext.md) and [**DxgkDdiDestroyContext**](./nc-d3dkmddi-dxgkddi_destroycontext.md) functions) and the use of a device context (through the [**DxgkDdiPresent**](./nc-d3dkmddi-dxgkddi_present.md) and [**DxgkDdiRender**](./nc-d3dkmddi-dxgkddi_render.md) functions). If the driver does not support context creation, for every call to the driver that would pass a handle to a context, the Microsoft DirectX graphics kernel subsystem replaces the handle to the context with a handle to the device.

### -field VSyncPowerSaveAware

A UINT value that specifies whether the driver supports vertical-sync power-saving functionality.

If **VSyncPowerSaveAware** is set to 1 (TRUE), the OS can save power by disabling and enabling the vertical-sync interrupt that occurs from the usage of some applications. If **VSyncPowerSaveAware** is set to zero (FALSE), the OS will never disable the vertical-sync interrupt for applications that might cause the vertical-sync interrupt to occur. Supported starting with Windows Server 2008 and Windows Vista with SP1.

### -field PreemptionAware

A UINT value that specifies whether the driver supports the GPU preemption policy of Windows 8 and later versions of Windows. With this policy, the OS always issues preemption requests to the GPU before it initiates the [**Timeout Detection and Recovery
(TDR)](/windows-hardware/drivers/display/timeout-detection-and-recovery) process. Supported starting with Windows 8.

If **PreemptionAware** is set to 1 (TRUE), the driver supports the preemption policy of Windows 8 and later versions of Windows. Note that if **PreemptionAware** is set to 1, the **MultiEngineAware** member must also be set to a value of 1. If **PreemptionAware** is set to 1 but **MultiEngineAware** is set to zero, the OS will halt the driver initialization process and return a failure code.

If **PreemptionAware** is set to zero (FALSE), the driver supports the preemption policy of Windows 7. With this policy, the OS may not issue preemption requests while potentially long running operations are being executed on the GPU. As a result, these GPU requests are not preempted  before the TDR process is initiated. This may cause the TDR process to repeatedly reset the GPU which could lead to a system stop error.

### -field NoDmaPatching

A UINT value that specifies whether the driver disables leak detection for DMA buffers that are split into multiple parts. This detection is performed after the driver's [**DxgkDdiPatch**](./nc-d3dkmddi-dxgkddi_patch.md) function is called to assign, or *patch*, physical addresses to each part of the DMA buffer. Supported starting with Windows 8.

Display devices that support virtual addresses can reprogram a virtual address to a new video memory location without having to patch the value of the DMA buffer address. For these types of display devices, the driver should set **NoDmaPatching** to 1.

If **NoDmaPatching** is set to 1 (TRUE), the driver disables leak detection, and the behavior of DMA buffer splitting is the same as in Windows 7. Note that when **NoDmaPatching** is set to 1, the **PreemptionAware** and **MultiEngineAware** members must also be set to 1. If **NoDmaPatching** is set to 1 but **PreemptionAware** or **MultiEngineAware** are set to zero, the OS will halt the driver initialization process and return a failure code.

If **NoDmaPatching** is set to 0 (FALSE), the driver enables leak detection for patched DMA buffer addresses. The OS performs leak detection before it calls the driver's [**DxgkDdiPatch**](./nc-d3dkmddi-dxgkddi_patch.md) function.

### -field CancelCommandAware

A UINT value that specifies whether the driver supports cleaning up internal resources (through the [**DxgkDdiCancelCommand**](./nc-d3dkmddi-dxgkddi_cancelcommand.md) function) after a command is removed from the hardware queue. Supported starting with Windows 8.

If **CancelCommandAware** is set to 1 (TRUE), the driver supports cleaning up resources associated with a canceled DMA packet. Note that when **CancelCommandAware** is set to 1, the **MultiEngineAware** member must also be set to 1. If **CancelCommandAware** is set to 1 but **MultiEngineAware** is set to zero, the OS returns a failure code.

If **CancelCommandAware** is set to zero (FALSE), the driver does not support cleaning up resources.

### -field No64BitAtomics

If **No64BitAtomics** is set to 1 (TRUE), the driver indicates that the GPU is capable of only updating 32 bit values atomically. In this case, the OS will handle the fence wraparound case automatically, however it will place a restriction that an outstanding wait and signal fence values cannot be more than UINT_MAX/2 apart from the last signaled fence value. Supported starting with Windows 10.

If **No64BitAtomics** is set to zero (FALSE), the driver indicates that the GPU is capable of updating 64 bit values atomically as visible by the CPU.

### -field LowIrqlPreemptCommand

### -field HwQueuePacketCap

Maximum number of DMA packets allowed to be queued to a node.

### -field NativeGpuFence

If the OS has enabled the [**DXGK_FEATURE_NATIVE_FENCE**](../d3dukmdt/ne-d3dukmdt-dxgk_feature_id.md) feature, the driver can declare support for native GPU fence functionality during adapter initialization by setting the **NativeGpuFence** bit to 1. This capability is exposed to user mode via a corresponding [**D3DKMT_WDDM_3_1_CAPS::NativeGpuFenceSupported**](../d3dkmdt/ns-d3dkmdt-d3dkmt_wddm_3_1_caps.md) bit. For more information, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects). Available starting with Windows 11, version 22H2 (WDDM 3.1).

### -field OptimizedNativeFenceSignaledInterrupt

The driver sets this TRUE if, on a signaled interrupt, the GPU can specify in [**DXGKARGCB_NOTIFY_INTERRUPT_DATA::NativeFenceSignaled**](ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md) only the KMD handle of the HWQueue that was running. For more information, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects). Available starting with Windows 11, version 22H2 (WDDM 3.1).

### -field Reserved

This member is reserved and should be set to zero.

### -field Value

An alternative way to access the bit-field flags in the union.

## -see-also

[**DXGK_DRIVERCAPS**](./ns-d3dkmddi-_dxgk_drivercaps.md)

[**DxgkDdiCancelCommand**](./nc-d3dkmddi-dxgkddi_cancelcommand.md)

[**DxgkDdiCreateContext**](./nc-d3dkmddi-dxgkddi_createcontext.md)

[**DxgkDdiDestroyContext**](./nc-d3dkmddi-dxgkddi_destroycontext.md)

[**DxgkDdiPatch**](./nc-d3dkmddi-dxgkddi_patch.md)

[**DxgkDdiPresent**](./nc-d3dkmddi-dxgkddi_present.md)

[**DxgkDdiRender**](./nc-d3dkmddi-dxgkddi_render.md)
