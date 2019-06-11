---
UID: NS:d3d10umddi.D3D10DDIARG_CREATEDEVICE
title: D3D10DDIARG_CREATEDEVICE (d3d10umddi.h)
description: The D3D10DDIARG_CREATEDEVICE structure describes the display device to create.
old-location: display\d3d10ddiarg_createdevice.htm
ms.assetid: 64154d8a-1775-455b-bf31-9c3a0f1398ad
ms.date: 05/10/2018
ms.keywords: D3D10DDIARG_CREATEDEVICE, D3D10DDIARG_CREATEDEVICE structure [Display Devices], UMDisplayDriver_Dx10param_Structs_cf670d46-fffb-49ec-8d04-61f73e30e309.xml, d3d10umddi/D3D10DDIARG_CREATEDEVICE, display.d3d10ddiarg_createdevice
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d10umddi.h
api_name:
- D3D10DDIARG_CREATEDEVICE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10DDIARG_CREATEDEVICE
ms.custom: 19H1
---

# D3D10DDIARG_CREATEDEVICE structure


## -description


The <b>D3D10DDIARG_CREATEDEVICE</b> structure describes the display device to create.


## -struct-fields




### -field hRTDevice

[in] A handle to the display device (graphics context) that specifies the handle that the driver should use when it calls back into the Direct3D runtime (that is, when the driver calls functions that the <b>pKTCallbacks</b> member specifies). 


### -field Interface

[in] The Direct3D interface version. The high 16 bits store the major release number (such as 10, 11, and so on); the low 16 bits store the minor release number (such as 0, 1, 2, and so on). The minor release number will be increased when a change to the interface is released.


### -field Version

[in] A number that the driver can use to identify when the Direct3D runtime was built. The high 16 bits represent the build number; the low 16 bits represent the revision number. 

The driver is required only to monitor the high 16 bits. The driver should ensure that the runtime build version that is passed in is greater than or equal to the current build version of the driver. The driver should return a failure from its <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> function if the passed in build version is incompatible. 


### -field pKTCallbacks

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544512">D3DDDI_DEVICECALLBACKS</a> structure that contains a table of Direct3D runtime callback functions that the driver can use to access kernel services.


### -field pDeviceFuncs

[in/out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a> structure that the user-mode display driver fills with a table of its functions. The Direct3D runtime uses these functions to communicate with the user-mode display driver.

The driver should fill its Direct3D version 10.0 functions in the supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a> structure when the value in the <b>Interface</b> member is <b>D3D10_0_DDI_INTERFACE_VERSION</b>.  


### -field p10_1DeviceFuncs

[in/out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541873">D3D10_1DDI_DEVICEFUNCS</a> structure that the user-mode display driver fills with a table of its functions. Version 10.1 of the Direct3D runtime uses these functions to communicate with the user-mode display driver.

The driver should fill its Direct3D version 10.1 functions in the supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff541873">D3D10_1DDI_DEVICEFUNCS</a> structure when the value in the <b>Interface</b> member is <b>D3D10_1_DDI_INTERFACE_VERSION</b>. 

Supported starting with Windows Vista with SP1 and Windows Server 2008.


### -field p11DeviceFuncs

[in/out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a> structure that the user-mode display driver fills with a table of its functions. Version 11 of the Direct3D runtime uses these functions to communicate with the user-mode display driver.

The driver should fill its Direct3D version 11.0 functions in the supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a> structure when the value in the <b>Interface</b> member is <b>D3D11_0_DDI_INTERFACE_VERSION</b>.  

Supported starting with Windows 7.


### -field p11_1DeviceFuncs

[in/out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406443">D3D11_1DDI_DEVICEFUNCS</a> structure that the user-mode display driver fills with a table of its functions. Starting with version 11.1, the Direct3D runtime uses these functions to communicate with the user-mode display driver.

The driver should fill its Direct3D version 11.1 functions in the supplied <a href="https://msdn.microsoft.com/library/windows/hardware/hh406443">D3D11_1DDI_DEVICEFUNCS</a> structure when the value in the <b>Interface</b> member is <b>D3D11_1_DDI_INTERFACE_VERSION</b>.

Supported starting with Windows 8.


### -field pWDDM1_3DeviceFuncs

[in/out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn458988">D3DWDDM1_3DDI_DEVICEFUNCS</a> structure that the user-mode display driver fills with a table of its functions. Version 11.2 of the Direct3D runtime uses these functions to communicate with the user-mode display driver.

The driver should fill its Direct3D version 11.2 functions in the supplied <a href="https://msdn.microsoft.com/library/windows/hardware/dn458988">D3DWDDM1_3DDI_DEVICEFUNCS</a> structure when the value in the <b>Interface</b> member is <b>D3DWDDM1_3_DDI_INTERFACE_VERSION</b>.

Supported starting with Windows 8.1.


### -field pWDDM2_0DeviceFuncs

 


### -field pWDDM2_1DeviceFuncs

 


### -field pWDDM2_2DeviceFuncs

 
### -field pWDDM2_6DeviceFuncs

Supported starting with Windows 10, version 1901.

### -field hDrvDevice

[in/out] A handle to the display device (graphics context) that the Direct3D runtime uses in subsequent driver calls to identify the display device.


### -field DXGIBaseDDI

[in/out] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff557485">DXGI_DDI_BASE_ARGS</a> structure that provides access to the DXGI. The DXGI DDI handles low-level tasks like presenting rendered frames to an output, controlling gamma, and managing a full-screen transition. 


### -field hRTCoreLayer

[in] A handle that the driver should use when it calls back into the Direct3D runtime to access core Direct3D 10 functionality (that is, when the driver calls functions that the <b>pUMCallbacks</b> member specifies). 


### -field pUMCallbacks

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541820">D3D10DDI_CORELAYER_DEVICECALLBACKS</a> structure that contains a table of Direct3D 10 runtime callback functions that the driver can use to access core user-mode runtime functionality. 


### -field p11UMCallbacks

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542137">D3D11DDI_CORELAYER_DEVICECALLBACKS</a> structure that contains a table of Direct3D 11 runtime callback functions, which the driver can use to access core user-mode runtime functionality.

Supported starting with Windows 7.


### -field pWDDM2_0UMCallbacks

 


### -field pWDDM2_2UMCallbacks

 


### -field Flags

[in] A valid bitwise OR of flag values that identify how to create the display device. The Direct3D runtime supports the following flags:  





#### D3D10DDI_CREATEDEVICE_FLAG_DISABLE_EXTRA_THREAD_CREATION (0x1)

If this flag is set, the user-mode display driver should not run multiple threads simultaneously when it processes calls to its functions from the Direct3D runtime. A driver can typically start and run multiple threads to process operations faster, unless the <b>D3D10DDI_CREATEDEVICE_FLAG_DISABLE_EXTRA_THREAD_CREATION</b> flag is set.



#### D3D11DDI_CREATEDEVICE_FLAG_SINGLETHREADED (0x10)

This flag informs the user-mode display driver that the application is single threaded. The Direct3D 11 runtime allows multiple application threads to enter the driver if the driver allows this mode of operation. However, not all applications can run multiple threads. If this flag is set, the driver does not expect multiple threads to enter it and run simultaneously. The driver can avoid synchronization if this flag is set.

Supported starting with Windows 7.



#### The flag that is set in the 0xE mask of the Flags member

This flag represents the level of 3-D pipeline that the driver should support for the display device. The driver uses the following constant and macros to extract one of the values from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542126">D3D11DDI_3DPIPELINELEVEL</a> enumeration that represent the 3-D pipeline level to support. The value in the <b>Flags</b> member is formatted like the <b>Caps</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542134">D3D11DDI_3DPIPELINESUPPORT_CAPS</a> structure.

```cpp
#define D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_SHIFT (0x1)
#define D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_MASK (0x7 &lt;&lt; D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_SHIFT)
#define D3D11DDI_EXTRACT_3DPIPELINELEVEL_FROM_FLAGS( Flags ) \
    ((D3D11DDI_3DPIPELINELEVEL)(((Flags) & D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_MASK) >> \
    D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_SHIFT))
```

Supported starting with Windows 7.


### -field ppfnRetrieveSubObject

[in/out] A pointer to a <a href="https://msdn.microsoft.com/9029ec8d-102f-4d83-8ab5-fc208d8b5249">RetrieveSubObject(D3D11_1)</a> function that retrieves subparts of a Direct3D driver device object.

Supported starting with Windows 8.


## -remarks



The driver examines values in the <b>Interface</b> and <b>Version</b> members to determine whether to fill the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff541873">D3D10_1DDI_DEVICEFUNCS</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh406443">D3D11_1DDI_DEVICEFUNCS</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/dn458988">D3DWDDM1_3DDI_DEVICEFUNCS</a> structure that the <b>pDeviceFuncs</b>, <b>p10_1DeviceFuncs</b>, <b>p11DeviceFuncs</b>, <b>p11_1DeviceFuncs</b>, or  <b>pWDDM1_3DeviceFuncs</b> member points to with the driver's functions. The following constants from D3d10umddi.h are examples of the constants that the driver might find in <b>Interface</b> and <b>Version</b>:

```cpp
#define D3D10_1_DDI_MINOR_VERSION 2
#define D3D10_1_DDI_INTERFACE_VERSION ((D3D10_DDI_MAJOR_VERSION &lt;&lt; 16) | D3D10_1_DDI_MINOR_VERSION)
#define D3D10_1_DDI_BUILD_VERSION 1
#define D3D10_1_DDI_SUPPORTED ((((UINT64)D3D10_1_DDI_INTERFACE_VERSION) &lt;&lt; 32) | (((UINT64)D3D10_1_DDI_BUILD_VERSION) &lt;&lt; 16))
```

Other possible combinations of constants for different versions of the operating system, Direct3D, and Windows Display Driver Model (WDDM) are listed in the D3d10umddi.h header.




## -see-also




<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541820">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541873">D3D10_1DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542126">D3D11DDI_3DPIPELINELEVEL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542134">D3D11DDI_3DPIPELINESUPPORT_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542137">D3D11DDI_CORELAYER_DEVICECALLBACKS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406443">D3D11_1DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544375">D3DDDI_ALLOCATIONLIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544512">D3DDDI_DEVICECALLBACKS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544630">D3DDDI_PATCHLOCATIONLIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn458988">D3DWDDM1_3DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557485">DXGI_DDI_BASE_ARGS</a>



<a href="https://msdn.microsoft.com/a7027735-0ec4-4fad-81fb-1c3aca4ebf2d">DxgkDdiCreateDevice</a>



<a href="https://msdn.microsoft.com/9029ec8d-102f-4d83-8ab5-fc208d8b5249">RetrieveSubObject(D3D11_1)</a>
 

 

