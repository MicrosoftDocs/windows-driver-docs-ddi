---
UID: NS:d3d10umddi.D3D11DDIARG_CREATEDEFERREDCONTEXT
title: D3D11DDIARG_CREATEDEFERREDCONTEXT (d3d10umddi.h)
description: The D3D11DDIARG_CREATEDEFERREDCONTEXT structure describes the deferred context to create.
old-location: display\d3d11ddiarg_createdeferredcontext.htm
ms.assetid: 4486939d-a35c-4b0b-b0d0-6402a62a4870
ms.date: 05/10/2018
ms.keywords: D3D11DDIARG_CREATEDEFERREDCONTEXT, D3D11DDIARG_CREATEDEFERREDCONTEXT structure [Display Devices], UMDisplayDriver_Dx11param_Structs_c66ddced-4073-4400-8142-4464ceadad74.xml, d3d10umddi/D3D11DDIARG_CREATEDEFERREDCONTEXT, display.d3d11ddiarg_createdeferredcontext
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 7
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
- D3D11DDIARG_CREATEDEFERREDCONTEXT
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11DDIARG_CREATEDEFERREDCONTEXT
ms.custom: 19H1
---

# D3D11DDIARG_CREATEDEFERREDCONTEXT structure


## -description


The D3D11DDIARG_CREATEDEFERREDCONTEXT structure describes the deferred context to create. 


## -struct-fields




### -field p11ContextFuncs

[in/out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a> structure that the user-mode display driver fills with a table of its functions for the deferred context. The Direct3D runtime uses these functions to communicate with the user-mode display driver.

For a list of the functions that are not leveraged for deferred contexts, see <a href="https://msdn.microsoft.com/f6e7898a-7fb8-4a70-ab2e-3372a28db6f4">Excluding DDI Functions for Deferred Contexts</a>. 


### -field p11_1ContextFuncs

[in/out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406443">D3D11_1DDI_DEVICEFUNCS</a> structure that the user-mode display driver fills with a table of its functions for the deferred context. The Direct3D runtime uses these functions to communicate with the user-mode display driver.

Supported starting with Windows 8.


### -field pWDDM1_3ContextFuncs

[in/out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn458988">D3DWDDM1_3DDI_DEVICEFUNCS</a> structure that the user-mode display driver fills with a table of its functions for the deferred context. The Direct3D runtime uses these functions to communicate with the user-mode display driver.

Supported starting with Windows 8.1.


### -field pWDDM2_0ContextFuncs

 


### -field pWDDM2_1ContextFuncs

 


### -field pWDDM2_2ContextFuncs

### -field pWDDM2_6ContextFuncs


### -field hDrvContext

[in] A handle to the driver context for the driver-private handle storage. 


### -field hRTCoreLayer

[in] A handle that the driver should use when it calls back into the Direct3D runtime to access core Direct3D 11 functionality (that is, when the driver calls functions that the <b>p11UMCallbacks</b> member specifies). 


### -field p11UMCallbacks

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542137">D3D11DDI_CORELAYER_DEVICECALLBACKS</a> structure that contains a table of Direct3D 11 runtime callback functions that the driver can use to access core user-mode runtime functionality. 


### -field pWDDM2_0UMCallbacks

 


### -field pWDDM2_2UMCallbacks

 


### -field Flags

[in] A valid bitwise OR of flag values that identify how to create a rendering device. The Direct3D runtime supports the following flags:  





#### D3D10DDI_CREATEDEVICE_FLAG_DISABLE_EXTRA_THREAD_CREATION (0x1)

If this flag is set, the user-mode display driver should not run multiple threads simultaneously when it processes calls to its functions from the Direct3D runtime. A driver can typically start and run multiple threads to process operations faster, unless D3D10DDI_CREATEDEVICE_FLAG_DISABLE_EXTRA_THREAD_CREATION is set.



#### D3D11DDI_CREATEDEVICE_FLAG_SINGLETHREADED (0x10)

This flag informs the user-mode display driver that the application is single threaded. The Direct3D version 11 runtime allows multiple application threads to enter the driver if the driver allows this mode of operation. However, not all applications can run multiple threads. If this flag is set, the driver will not expect multiple threads to enter it and run simultaneously. The driver can avoid synchronization if this flag is present.



#### The flag that is set in the 0xE mask of the Flags member

This flag represents the level of 3-D pipeline that the driver should support for the display device. The driver uses the following constant and macros to extract one of the values from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542126">D3D11DDI_3DPIPELINELEVEL</a> enumeration that represent the 3-D pipeline level to support. The value in the <b>Flags</b> member is formatted like the <b>Caps</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542134">D3D11DDI_3DPIPELINESUPPORT_CAPS</a> structure.

```cpp
#define D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_SHIFT (0x1)
#define D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_MASK (0x7 &lt;&lt; D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_SHIFT)
#define D3D11DDI_EXTRACT_3DPIPELINELEVEL_FROM_FLAGS( Flags ) \
    ((D3D11DDI_3DPIPELINELEVEL)(((Flags) &amp; D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_MASK) &gt;&gt; \
    D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_SHIFT))
```

## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542126">D3D11DDI_3DPIPELINELEVEL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542134">D3D11DDI_3DPIPELINESUPPORT_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542137">D3D11DDI_CORELAYER_DEVICECALLBACKS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406443">D3D11_1DDI_DEVICEFUNCS</a>
 

 

