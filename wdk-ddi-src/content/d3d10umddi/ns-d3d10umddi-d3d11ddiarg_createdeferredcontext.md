---
UID: NS:d3d10umddi.D3D11DDIARG_CREATEDEFERREDCONTEXT
title: D3D11DDIARG_CREATEDEFERREDCONTEXT (d3d10umddi.h)
description: The D3D11DDIARG_CREATEDEFERREDCONTEXT structure describes the deferred context to create.
old-location: display\d3d11ddiarg_createdeferredcontext.htm
ms.date: 05/25/2022
keywords: ["D3D11DDIARG_CREATEDEFERREDCONTEXT structure"]
ms.keywords: D3D11DDIARG_CREATEDEFERREDCONTEXT, D3D11DDIARG_CREATEDEFERREDCONTEXT structure [Display Devices], UMDisplayDriver_Dx11param_Structs_c66ddced-4073-4400-8142-4464ceadad74.xml, d3d10umddi/D3D11DDIARG_CREATEDEFERREDCONTEXT, display.d3d11ddiarg_createdeferredcontext
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 7
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
req.typenames: D3D11DDIARG_CREATEDEFERREDCONTEXT
ms.custom: 19H1
f1_keywords:
 - D3D11DDIARG_CREATEDEFERREDCONTEXT
 - d3d10umddi/D3D11DDIARG_CREATEDEFERREDCONTEXT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D11DDIARG_CREATEDEFERREDCONTEXT
---

# D3D11DDIARG_CREATEDEFERREDCONTEXT structure

## -description

The D3D11DDIARG_CREATEDEFERREDCONTEXT structure describes the deferred context to create.

## -struct-fields

### -field p11ContextFuncs [in/out]

A pointer to a [**D3D11DDI_DEVICEFUNCS**](ns-d3d10umddi-d3d11ddi_devicefuncs.md) structure that the user-mode display driver fills with a table of its functions for the deferred context. The Direct3D runtime uses these functions to communicate with the user-mode display driver.

For a list of the functions that are not leveraged for deferred contexts, see [Excluding DDI Functions for Deferred Contexts](/windows-hardware/drivers/display/excluding-ddi-functions-for-deferred-contexts).

### -field p11_1ContextFuncs [in/out]

A pointer to a [**D3D11_1DDI_DEVICEFUNCS**](ns-d3d10umddi-d3d11_1ddi_devicefuncs.md) structure that the user-mode display driver fills with a table of its functions for the deferred context. The Direct3D runtime uses these functions to communicate with the user-mode display driver.

Supported starting with Windows 8.

### -field pWDDM1_3ContextFuncs [in/out]

A pointer to a [**D3DWDDM1_3DDI_DEVICEFUNCS**](ns-d3d10umddi-d3dwddm1_3ddi_devicefuncs.md) structure that the user-mode display driver fills with a table of its functions for the deferred context. The Direct3D runtime uses these functions to communicate with the user-mode display driver.

Supported starting with Windows 8.1.

### -field pWDDM2_0ContextFuncs [in/out]

Pointer to a [**D3DWDDM2_0DDI_DEVICEFUNCS**](ns-d3d10umddi-d3dwddm2_0ddi_devicefuncs.md) structure that the user-mode display driver fills its device function table for WDDM 2.0. The Direct3D runtime uses these functions to communicate with the user-mode display driver.

### -field pWDDM2_1ContextFuncs

Pointer to a [**D3DWDDM2_1DDI_DEVICEFUNCS**](ns-d3d10umddi-d3dwddm2_1ddi_devicefuncs.md) structure that the user-mode display driver fills its device function table for WDDM 2.1. The Direct3D runtime uses these functions to communicate with the user-mode display driver.

### -field pWDDM2_2ContextFuncs

Pointer to a [**D3DWDDM2_2DDI_DEVICEFUNCS**](ns-d3d10umddi-d3dwddm2_2ddi_devicefuncs.md) structure that the user-mode display driver fills its device function table for WDDM 2.2. The Direct3D runtime uses these functions to communicate with the user-mode display driver.

### -field pWDDM2_6ContextFuncs

Pointer to a [**D3DWDDM2_6DDI_DEVICEFUNCS**](ns-d3d10umddi-d3dwddm2_6ddi_devicefuncs.md) structure that the user-mode display driver fills its device function table for WDDM 2.6. The Direct3D runtime uses these functions to communicate with the user-mode display driver.

### -field hDrvContext [in]

A handle to the driver context for the driver-private handle storage.

### -field hRTCoreLayer [in]

A handle that the driver should use when it calls back into the Direct3D runtime to access core Direct3D 11 functionality (that is, when the driver calls functions that the **p11UMCallbacks** member specifies).

### -field p11UMCallbacks [in]

A pointer to a [**D3D11DDI_CORELAYER_DEVICECALLBACKS**](ns-d3d10umddi-d3d11ddi_corelayer_devicecallbacks.md) structure that contains the pre-WDDM 2.0 function table of Direct3D 11 runtime callback functions that the driver can use to access core user-mode runtime functionality.

### -field pWDDM2_0UMCallbacks

Pointer to a [**D3DWDDM2_0DDI_CORELAYER_DEVICECALLBACKS**](ns-d3d10umddi-d3dwddm2_0ddi_corelayer_devicecallbacks.md) structure that contains the WDDM 2.0 function table of Direct3D 11 core layer device callback functions that the driver can use to access core user-mode runtime functionality.

### -field pWDDM2_2UMCallbacks

Pointer to a [**D3DWDDM2_2DDI_CORELAYER_DEVICECALLBACKS**](ns-d3d10umddi-d3dwddm2_2ddi_corelayer_devicecallbacks.md) structure that contains the WDDM 2.2 function table of Direct3D 11 core layer device callback functions that the driver can use to access core user-mode runtime functionality.

### -field pWDDM2_6UMCallbacks

Pointer to a [**D3DWDDM2_6DDI_CORELAYER_DEVICECALLBACKS**](ns-d3d10umddi-d3dwddm2_6ddi_corelayer_devicecallbacks.md) structure that contains the WDDM 2.6 function table of Direct3D 11 core layer device callback functions that the driver can use to access core user-mode runtime functionality.

### -field Flags [in]

A valid bitwise OR of D3D10DDI_CREATEDEVICE_FLAG_*XXX* flag values that identify how to create a rendering device. The Direct3D runtime supports the following flags:  

| Flag | Meaning |
| ---- | ------- |
| D3D10DDI_CREATEDEVICE_FLAG_DISABLE_EXTRA_THREAD_CREATION (0x1) | When set, the user-mode display driver should not run multiple threads simultaneously when it processes calls to its functions from the Direct3D runtime. A driver can typically start and run multiple threads to process operations faster, unless D3D10DDI_CREATEDEVICE_FLAG_DISABLE_EXTRA_THREAD_CREATION is set. |
| D3D11DDI_CREATEDEVICE_FLAG_SINGLETHREADED (0x10) | This flag informs the user-mode display driver that the application is single threaded. The Direct3D version 11 runtime allows multiple application threads to enter the driver if the driver allows this mode of operation. However, not all applications can run multiple threads. If this flag is set, the driver will not expect multiple threads to enter it and run simultaneously. The driver can avoid synchronization if this flag is present. |
| The flag that is set in the 0xE mask of the Flags member | This flag represents the level of 3-D pipeline that the driver should support for the display device. The driver uses the following constant and macros to extract one of the values from the [**D3D11DDI_3DPIPELINELEVEL**](ne-d3d10umddi-d3d11ddi_3dpipelinelevel.md) enumeration that represent the 3-D pipeline level to support. |

The value in the **Flags** member is formatted like the **Caps** member of the [**D3D11DDI_3DPIPELINESUPPORT_CAPS**](ns-d3d10umddi-d3d11ddi_3dpipelinesupport_caps.md) structure.

```cpp
#define D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_SHIFT (0x1)
#define D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_MASK (0x7 << D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_SHIFT)
#define D3D11DDI_EXTRACT_3DPIPELINELEVEL_FROM_FLAGS( Flags ) \
    ((D3D11DDI_3DPIPELINELEVEL)(((Flags) & D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_MASK) >> \
    D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_SHIFT))
```

## -see-also

[**D3D11DDI_3DPIPELINELEVEL**](ne-d3d10umddi-d3d11ddi_3dpipelinelevel.md)

[**D3D11DDI_3DPIPELINESUPPORT_CAPS**](ns-d3d10umddi-d3d11ddi_3dpipelinesupport_caps.md)

[**D3D11DDI_CORELAYER_DEVICECALLBACKS**](ns-d3d10umddi-d3d11ddi_corelayer_devicecallbacks.md)

[**D3D11DDI_DEVICEFUNCS**](ns-d3d10umddi-d3d11ddi_devicefuncs.md)

[**D3D11_1DDI_DEVICEFUNCS**](ns-d3d10umddi-d3d11_1ddi_devicefuncs.md)
