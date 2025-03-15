---
UID: NS:d3dukmdt._D3DDDI_ESCAPEFLAGS
title: D3DDDI_ESCAPEFLAGS (d3dukmdt.h)
description: The D3DDDI_ESCAPEFLAGS structure identifies how the user-mode display driver shares information with the display miniport driver.
tech.root: display
ms.date: 02/06/2025
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista (WDDM 1.0)
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
req.typenames: D3DDDI_ESCAPEFLAGS
f1_keywords:
 - _D3DDDI_ESCAPEFLAGS
 - d3dukmdt/_D3DDDI_ESCAPEFLAGS
 - D3DDDI_ESCAPEFLAGS
 - d3dukmdt/D3DDDI_ESCAPEFLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _D3DDDI_ESCAPEFLAGS
 - D3DDDI_ESCAPEFLAGS
---

# D3DDDI_ESCAPEFLAGS structure

## -description

The **D3DDDI_ESCAPEFLAGS** structure identifies how the user-mode display driver (UMD) (or client driver) shares information with the kernel-mode display miniport driver (KMD).

## -struct-fields

### -field HardwareAccess

A UINT value that specifies whether the OS performs the [second level of synchronization](/windows-hardware/drivers/display/threading-and-synchronization-second-level) into the KMD for the [**DxgkDdiEscape**](../d3dkmddi/nc-d3dkmddi-dxgkddi_escape.md) call. If the driver requires the second level of synchronization and the **HardwareAccess** flag isn't set, the call to the driver's **DxgkDdiEscape** function should fail.

Starting in Windows 8.1,  if this member is set, **DeviceStatusQuery** and **ChangeFrameLatency** must be set to zero.

### -field DeviceStatusQuery

If set, when the [**pfnEscapeCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_escapecb.md) function is called and the [**D3DDDICB_ESCAPE**](../d3dumddi/ns-d3dumddi-_d3dddicb_escape.md).**PrivateDriverDataSize** member is ```sizeof(D3DDDI_EXECUTIONSTATEESCAPE)```, the Direct3D runtime interprets the **D3DDDICB_ESCAPE**.**pPrivateDriverData** member as a pointer to a buffer that contains a [**D3DDDI_EXECUTIONSTATEESCAPE**](../d3dumddi/ns-d3dumddi-_d3dddi_executionstateescape.md) structure. In addition, the runtime processes the **pfnEscapeCb** as a status query by writing the requested info into the provided buffer instead of sending a [**DxgkDdiEscape**](../d3dkmddi/nc-d3dkmddi-dxgkddi_escape.md) call to the KMD.

If this member is set, **HardwareAccess** and **ChangeFrameLatency** must be set to zero.

Supported starting with Windows 8.1.

The operating system ignores this member if it is prior to Windows 8.1, or if the user-mode driver was initialized with an **OpenAdapterXxx** call where the **pOpenData**->**Interface** member indicates Direct3D version 8 or earlier.

### -field ChangeFrameLatency

If set, when the [**pfnEscapeCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_escapecb.md) function is called, the [**D3DDDICB_ESCAPE**](../d3dumddi/ns-d3dumddi-_d3dddicb_escape.md).**PrivateDriverDataSize** member is ```sizeof(D3DDDI_FRAMELATENCYESCAPE)``` and conditions in Remarks are also met, the Direct3D runtime interprets the **D3DDDICB_ESCAPE**.**pPrivateDriverData** member as a pointer to a buffer that contains a [**D3DDDI_FRAMELATENCYESCAPE**](../d3dumddi/ns-d3dumddi-_d3dddi_framelatencyescape.md) structure. In addition, the runtime processes the **pfnEscapeCb** as a request to change the DirectX graphics kernel subsystem's maximum frame latency by writing the requested info into the provided buffer instead of sending a [**DxgkDdiEscape**](../d3dkmddi/nc-d3dkmddi-dxgkddi_escape.md) call to the KMD.

If this member is set, **HardwareAccess** and **DeviceStatusQuery** must be set to zero.

Supported starting with Windows 8.1.

The operating system ignores this member if it is prior to Windows 8.1, or if the user-mode driver was initialized with an **OpenAdapterXxx** call where the **pOpenData**->**Interface** member indicates Direct3D version 8 or earlier.

### -field NoAdapterSynchronization

### -field VirtualMachineData

Indicates that [**DxgkDdiEscape**](../d3dkmddi/nc-d3dkmddi-dxgkddi_escape.md) is called from a virtual machine. This flag can't be set from user mode. Supported starting with WDDM 2.2.

### -field DriverKnownEscape

The driver private data points to a well known structure.

### -field DriverCommonEscape

The private data points to a D3D runtime-defined structure.

### -field Reserved2

This member is reserved and should be set to zero.

### -field Reserved

This member is reserved and should be set to zero.

### -field Value

A member in the union that is contained in D3DDDI_ESCAPEFLAGS that can hold one 32-bit value that identifies how to share information.

## -remarks

If **ChangeFrameLatency** is set, a [**pfnEscapeCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_escapecb.md) call will succeed only if:

* The KMD is responsible for a linked adapter configuration (LDA) provided by a single vendor.
* The app has taken exclusive full-screen ownership of the display at some point in its lifetime.
* The app has not overridden the default maximum frame latency value of 3.

If these conditions are not met, **pfnEscapeCb** call returns an E_INVALIDARG error code.

## -see-also

[**D3DDDICB_ESCAPE**](../d3dumddi/ns-d3dumddi-_d3dddicb_escape.md)

[**D3DDDI_EXECUTIONSTATEESCAPE**](../d3dumddi/ns-d3dumddi-_d3dddi_executionstateescape.md)

[**D3DDDI_FRAMELATENCYESCAPE**](../d3dumddi/ns-d3dumddi-_d3dddi_framelatencyescape.md)

[**DXGKARG_ESCAPE**](../d3dkmddi/ns-d3dkmddi-_dxgkarg_escape.md)

[**DxgkDdiEscape**](../d3dkmddi/nc-d3dkmddi-dxgkddi_escape.md)

[**pfnEscapeCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_escapecb.md)
