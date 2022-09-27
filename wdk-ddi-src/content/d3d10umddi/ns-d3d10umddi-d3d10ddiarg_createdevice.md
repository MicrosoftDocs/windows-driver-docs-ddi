---
UID: NS:d3d10umddi.D3D10DDIARG_CREATEDEVICE
title: D3D10DDIARG_CREATEDEVICE (d3d10umddi.h)
description: The D3D10DDIARG_CREATEDEVICE structure describes the display device to create.
old-location: display\d3d10ddiarg_createdevice.htm
ms.date: 08/23/2022
keywords: ["D3D10DDIARG_CREATEDEVICE structure"]
ms.keywords: D3D10DDIARG_CREATEDEVICE, D3D10DDIARG_CREATEDEVICE structure [Display Devices], UMDisplayDriver_Dx10param_Structs_cf670d46-fffb-49ec-8d04-61f73e30e309.xml, d3d10umddi/D3D10DDIARG_CREATEDEVICE, display.d3d10ddiarg_createdevice
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
req.typenames: D3D10DDIARG_CREATEDEVICE
ms.custom: 19H1
f1_keywords:
 - D3D10DDIARG_CREATEDEVICE
 - d3d10umddi/D3D10DDIARG_CREATEDEVICE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D10DDIARG_CREATEDEVICE
---

# D3D10DDIARG_CREATEDEVICE structure

## -description

The **D3D10DDIARG_CREATEDEVICE** structure describes the display device to create.

## -struct-fields

### -field hRTDevice

[in] A handle to the display device (graphics context) that specifies the handle that the driver should use when it calls back into the Direct3D runtime (that is, when the driver calls functions that the **pKTCallbacks** member specifies).

### -field Interface

[in] The Direct3D interface version. The high 16 bits store the major release number (such as 10, 11, and so on); the low 16 bits store the minor release number (such as 0, 1, 2, and so on). The minor release number will be increased when a change to the interface is released.

### -field Version

[in] A number that the driver can use to identify when the Direct3D runtime was built. The high 16 bits represent the build number; the low 16 bits represent the revision number.

The driver is required only to monitor the high 16 bits. The driver should ensure that the runtime build version that is passed in is greater than or equal to the current build version of the driver. The driver should return a failure from its [**CreateDevice(D3D10)**](nc-d3d10umddi-pfnd3d10ddi_createdevice.md) function if the passed in build version is incompatible.

### -field pKTCallbacks

[in] A pointer to a [**D3DDDI_DEVICECALLBACKS**](../d3dumddi/ns-d3dumddi-_d3dddi_devicecallbacks.md) structure that contains a table of Direct3D runtime callback functions that the driver can use to access kernel services.

### -field pDeviceFuncs

[in/out] A pointer to a [**D3D10DDI_DEVICEFUNCS**](ns-d3d10umddi-d3d10ddi_devicefuncs.md) structure that the user-mode display driver fills with a table of its functions. The Direct3D runtime uses these functions to communicate with the user-mode display driver.

The driver should fill its Direct3D version 10.0 functions in the supplied [**D3D10DDI_DEVICEFUNCS**](ns-d3d10umddi-d3d10ddi_devicefuncs.md) structure when the value in the **Interface** member is **D3D10_0_DDI_INTERFACE_VERSION**.

### -field p10_1DeviceFuncs

[in/out] A pointer to a [**D3D10_1DDI_DEVICEFUNCS**](ns-d3d10umddi-d3d10_1ddi_devicefuncs.md) structure that the user-mode display driver fills with a table of its functions. Version 10.1 of the Direct3D runtime uses these functions to communicate with the user-mode display driver.

The driver should fill its Direct3D version 10.1 functions in the supplied [**D3D10_1DDI_DEVICEFUNCS**](ns-d3d10umddi-d3d10_1ddi_devicefuncs.md) structure when the value in the **Interface** member is **D3D10_1_DDI_INTERFACE_VERSION**.

Supported starting with Windows Vista with SP1 and Windows Server 2008.

### -field p11DeviceFuncs

[in/out] A pointer to a [**D3D11DDI_DEVICEFUNCS**](ns-d3d10umddi-d3d11ddi_devicefuncs.md) structure that the user-mode display driver fills with a table of its functions. Version 11 of the Direct3D runtime uses these functions to communicate with the user-mode display driver.

The driver should fill its Direct3D version 11.0 functions in the supplied [**D3D11DDI_DEVICEFUNCS**](ns-d3d10umddi-d3d11ddi_devicefuncs.md) structure when the value in the **Interface** member is **D3D11_0_DDI_INTERFACE_VERSION**.  

Supported starting with Windows 7.

### -field p11_1DeviceFuncs

[in/out] A pointer to a [**D3D11_1DDI_DEVICEFUNCS**](ns-d3d10umddi-d3d11_1ddi_devicefuncs.md) structure that the user-mode display driver fills with a table of its functions. Starting with version 11.1, the Direct3D runtime uses these functions to communicate with the user-mode display driver.

The driver should fill its Direct3D version 11.1 functions in the supplied [**D3D11_1DDI_DEVICEFUNCS**](ns-d3d10umddi-d3d11_1ddi_devicefuncs.md) structure when the value in the **Interface** member is **D3D11_1_DDI_INTERFACE_VERSION**.

Supported starting with Windows 8.

### -field pWDDM1_3DeviceFuncs

[in/out] A pointer to a [**D3DWDDM1_3DDI_DEVICEFUNCS**](ns-d3d10umddi-d3dwddm1_3ddi_devicefuncs.md) structure that the user-mode display driver fills with a table of its functions. Version 11.2 of the Direct3D runtime uses these functions to communicate with the user-mode display driver.

The driver should fill its Direct3D version 11.2 functions in the supplied [**D3DWDDM1_3DDI_DEVICEFUNCS**](ns-d3d10umddi-d3dwddm1_3ddi_devicefuncs.md) structure when the value in the **Interface** member is **D3DWDDM1_3_DDI_INTERFACE_VERSION**.

Supported starting with Windows 8.1.

### -field pWDDM2_0DeviceFuncs

[in/out] A pointer to a [**D3DWDDM2_0DDI_DEVICEFUNCS**](ns-d3d10umddi-d3dwddm2_0ddi_devicefuncs.md) structure that the user-mode display driver fills with a table of its functions. The driver should fill its Direct3D functions in the supplied structure when the value in the **Interface** member is **D3DWDDM2_0_DDI_INTERFACE_VERSION**.

### -field pWDDM2_1DeviceFuncs

[in/out] A pointer to a [**D3DWDDM2_1DDI_DEVICEFUNCS**](ns-d3d10umddi-d3dwddm2_1ddi_devicefuncs.md) structure that the user-mode display driver fills with a table of its functions. The driver should fill its Direct3D functions in the supplied structure when the value in the **Interface** member is **D3DWDDM2_0_DDI_INTERFACE_VERSION**.

### -field pWDDM2_2DeviceFuncs

[in/out] A pointer to a [**D3DWDDM2_2DDI_DEVICEFUNCS**](ns-d3d10umddi-d3dwddm2_2ddi_devicefuncs.md) structure that the user-mode display driver fills with a table of its functions. The driver should fill its Direct3D functions in the supplied structure when the value in the **Interface** member is **D3DWDDM2_0_DDI_INTERFACE_VERSION**.

### -field pWDDM2_6DeviceFuncs

[in/out] A pointer to a [**D3DWDDM2_6DDI_DEVICEFUNCS**](ns-d3d10umddi-d3dwddm2_6ddi_devicefuncs.md) structure that the user-mode display driver fills with a table of its functions. The driver should fill its Direct3D functions in the supplied structure when the value in the **Interface** member is **D3DWDDM2_0_DDI_INTERFACE_VERSION**.

Supported starting with Windows 10, version 1901.

### -field hDrvDevice

[in/out] A handle to the display device (graphics context) that the Direct3D runtime uses in subsequent driver calls to identify the display device.

### -field DXGIBaseDDI

[in/out] A [**DXGI_DDI_BASE_ARGS**](../dxgiddi/ns-dxgiddi-dxgi_ddi_base_args.md) structure that provides access to the DXGI. The DXGI DDI handles low-level tasks like presenting rendered frames to an output, controlling gamma, and managing a full-screen transition.

### -field hRTCoreLayer

[in] A handle that the driver should use when it calls back into the Direct3D runtime to access core Direct3D 10 functionality (that is, when the driver calls functions that the **pUMCallbacks** member specifies).

### -field pUMCallbacks

[in] A pointer to a [**D3D10DDI_CORELAYER_DEVICECALLBACKS**](ns-d3d10umddi-d3d10ddi_corelayer_devicecallbacks.md) structure that contains a table of Direct3D 10 runtime callback functions that the driver can use to access core user-mode runtime functionality.

### -field p11UMCallbacks

[in] A pointer to a [**D3D11DDI_CORELAYER_DEVICECALLBACKS**](ns-d3d10umddi-d3d11ddi_corelayer_devicecallbacks.md) structure that contains a table of Direct3D 10 and Direct3D 11 runtime callback functions, which the driver can use to access core user-mode runtime functionality.

Supported starting with Windows 7.

### -field pWDDM2_0UMCallbacks

[in] Pointer to a [**D3DWDDM2_0DDI_CORELAYER_DEVICECALLBACKS**](ns-d3d10umddi-d3dwddm2_0ddi_corelayer_devicecallbacks.md) structure that contains a table of Direct3D 10, Direct3D 11, and WDDM 2.0 runtime callback functions, which the driver can use to access core user-mode runtime functionality.

### -field pWDDM2_2UMCallbacks

[in] Pointer to a [**D3DWDDM2_2DDI_CORELAYER_DEVICECALLBACKS**](ns-d3d10umddi-d3dwddm2_2ddi_corelayer_devicecallbacks.md) structure that contains a table of Direct3D 10, Direct3D 11, WDDM 2.0, and WDDM 2.2 runtime callback functions, which the driver can use to access core user-mode runtime functionality.

### -field pWDDM2_6UMCallbacks

[in] Pointer to a [**D3DWDDM2_6DDI_CORELAYER_DEVICECALLBACKS**](ns-d3d10umddi-d3dwddm2_6ddi_corelayer_devicecallbacks.md) structure that contains a table of Direct3D 10, Direct3D 11, WDDM 2.0, WDDM 2.2, and WDDM 2.6 runtime callback functions, which the driver can use to access core user-mode runtime functionality.

### -field Flags

[in] A valid bitwise OR of flag values that identify how to create the display device. The Direct3D runtime supports the following flags:  

| Flag | Meaning |
| ---- | ------- |
| D3D10DDI_CREATEDEVICE_FLAG_DISABLE_EXTRA_THREAD_CREATION (0x1) | If this flag is set, the user-mode display driver should not run multiple threads simultaneously when it processes calls to its functions from the Direct3D runtime. A driver can typically start and run multiple threads to process operations faster, unless the **D3D10DDI_CREATEDEVICE_FLAG_DISABLE_EXTRA_THREAD_CREATION** flag is set. |
| D3D11DDI_CREATEDEVICE_FLAG_SINGLETHREADED (0x10) | Informs the user-mode display driver that the application is single threaded. The Direct3D 11 runtime allows multiple application threads to enter the driver if the driver allows this mode of operation. However, not all applications can run multiple threads. If this flag is set, the driver does not expect multiple threads to enter it and run simultaneously. The driver can avoid synchronization if this flag is set. Supported starting with Windows 7. |
| The flag that is set in the 0xE mask of the **Flags** member | Represents the level of 3-D pipeline that the driver should support for the display device. See Remarks. Supported starting with Windows 7. |

### -field ppfnRetrieveSubObject

[in/out] A pointer to a [**RetrieveSubObject(D3D11_1)**](nc-d3d10umddi-pfnd3d10ddi_retrievesubobject.md) function that retrieves subparts of a Direct3D driver device object.

Supported starting with Windows 8.

## -remarks

The driver examines values in the **Interface** and **Version** members to determine whether to fill the [**D3D10DDI_DEVICEFUNCS**](ns-d3d10umddi-d3d10ddi_devicefuncs.md), [**D3D10_1DDI_DEVICEFUNCS**](ns-d3d10umddi-d3d10_1ddi_devicefuncs.md), [**D3D11DDI_DEVICEFUNCS**](ns-d3d10umddi-d3d11ddi_devicefuncs.md), [**D3D11_1DDI_DEVICEFUNCS**](ns-d3d10umddi-d3d11_1ddi_devicefuncs.md), or [**D3DWDDM1_3DDI_DEVICEFUNCS**](ns-d3d10umddi-d3dwddm1_3ddi_devicefuncs.md) structure that the **pDeviceFuncs**, **p10_1DeviceFuncs**, **p11DeviceFuncs**, **p11_1DeviceFuncs**, or  **pWDDM1_3DeviceFuncs** member points to with the driver's functions. The following constants from D3d10umddi.h are examples of the constants that the driver might find in **Interface** and **Version**:

```cpp
#define D3D10_1_DDI_MINOR_VERSION 2
#define D3D10_1_DDI_INTERFACE_VERSION ((D3D10_DDI_MAJOR_VERSION << 16) | D3D10_1_DDI_MINOR_VERSION)
#define D3D10_1_DDI_BUILD_VERSION 1
#define D3D10_1_DDI_SUPPORTED ((((UINT64)D3D10_1_DDI_INTERFACE_VERSION) << 32) | (((UINT64)D3D10_1_DDI_BUILD_VERSION) << 16))
```

Other possible combinations of constants for different versions of the operating system, Direct3D, and Windows Display Driver Model (WDDM) are listed in the *D3d10umddi.h* header.

 For the flag that is set in the 0xE mask of the **Flags** member, the driver uses the following constant and macros to extract one of the values from the [**D3D11DDI_3DPIPELINELEVEL**](ne-d3d10umddi-d3d11ddi_3dpipelinelevel.md) enumeration that represent the 3-D pipeline level to support. The value in the **Flags** member is formatted like the **Caps** member of the [**D3D11DDI_3DPIPELINESUPPORT_CAPS**](ns-d3d10umddi-d3d11ddi_3dpipelinesupport_caps.md) structure.

```cpp
#define D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_SHIFT (0x1)
#define D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_MASK (0x7 << D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_SHIFT)
#define D3D11DDI_EXTRACT_3DPIPELINELEVEL_FROM_FLAGS( Flags ) \
    ((D3D11DDI_3DPIPELINELEVEL)(((Flags) & D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_MASK) >> \
    D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_SHIFT))
```

## -see-also

[**CreateDevice(D3D10)**](nc-d3d10umddi-pfnd3d10ddi_createdevice.md)

[**D3D10DDI_CORELAYER_DEVICECALLBACKS**](ns-d3d10umddi-d3d10ddi_corelayer_devicecallbacks.md)

[**D3D10DDI_DEVICEFUNCS**](ns-d3d10umddi-d3d10ddi_devicefuncs.md)

[**D3D10_1DDI_DEVICEFUNCS**](ns-d3d10umddi-d3d10_1ddi_devicefuncs.md)

[**D3D11DDI_3DPIPELINELEVEL**](ne-d3d10umddi-d3d11ddi_3dpipelinelevel.md)

[**D3D11DDI_3DPIPELINESUPPORT_CAPS**](ns-d3d10umddi-d3d11ddi_3dpipelinesupport_caps.md)

[**D3D11DDI_CORELAYER_DEVICECALLBACKS**](ns-d3d10umddi-d3d11ddi_corelayer_devicecallbacks.md)

[**D3D11DDI_DEVICEFUNCS**](ns-d3d10umddi-d3d11ddi_devicefuncs.md)

[**D3D11_1DDI_DEVICEFUNCS**](ns-d3d10umddi-d3d11_1ddi_devicefuncs.md)

[**D3DDDI_ALLOCATIONLIST**](../d3dukmdt/ns-d3dukmdt-_d3dddi_allocationlist.md)

[**D3DDDI_DEVICECALLBACKS**](../d3dumddi/ns-d3dumddi-_d3dddi_devicecallbacks.md)

[**D3DDDI_PATCHLOCATIONLIST**](../d3dukmdt/ns-d3dukmdt-_d3dddi_patchlocationlist.md)

[**D3DWDDM1_3DDI_DEVICEFUNCS**](ns-d3d10umddi-d3dwddm1_3ddi_devicefuncs.md)

[**DXGI_DDI_BASE_ARGS**](../dxgiddi/ns-dxgiddi-dxgi_ddi_base_args.md)

[**DxgkDdiCreateDevice**](../d3dkmddi/nc-d3dkmddi-dxgkddi_createdevice.md)

[**RetrieveSubObject(D3D11_1)**](nc-d3d10umddi-pfnd3d10ddi_retrievesubobject.md)
