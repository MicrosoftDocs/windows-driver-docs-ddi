---
UID: NS:d3d10umddi.D3D11DDIARG_CREATEDEFERREDCONTEXT
title: D3D11DDIARG_CREATEDEFERREDCONTEXT
author: windows-driver-content
description: The D3D11DDIARG_CREATEDEFERREDCONTEXT structure describes the deferred context to create.
old-location: display\d3d11ddiarg_createdeferredcontext.htm
old-project: display
ms.assetid: 4486939d-a35c-4b0b-b0d0-6402a62a4870
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 1, 3, A, C, D, D3D11DDIARG_CREATEDEFERREDCONTEXT, D3D11DDIARG_CREATEDEFERREDCONTEXT structure [Display Devices], E, F, G, I, N, O, R, T, UMDisplayDriver_Dx11param_Structs_c66ddced-4073-4400-8142-4464ceadad74.xml, X, _, d3d10umddi/D3D11DDIARG_CREATEDEFERREDCONTEXT, display.d3d11ddiarg_createdeferredcontext"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDIARG_CALCPRIVATEDEFERREDCONTEXTSIZE is supported beginning with the Windows 7 operating system.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3d10umddi.h
apiname:
-	D3D11DDIARG_CREATEDEFERREDCONTEXT
product: Windows
targetos: Windows
req.typenames: D3D11DDIARG_CREATEDEFERREDCONTEXT
---

# D3D11DDIARG_CREATEDEFERREDCONTEXT structure


## -description


The D3D11DDIARG_CREATEDEFERREDCONTEXT structure describes the deferred context to create. 


## -syntax


````
typedef struct D3D11DDIARG_CREATEDEFERREDCONTEXT {
  union {
    struct D3D11DDI_DEVICEFUNCS  *p11ContextFuncs;
    struct D3D11_1DDI_DEVICEFUNCS  *p11_1ContextFuncs;
#if D3D11DDI_MINOR_HEADER_VERSION >= 4
    struct D3DWDDM1_3DDI_DEVICEFUNCS  *pWDDM1_3ContextFuncs;
#endif 
  };
  D3D10DDI_HDEVICE      hDrvContext;
  D3D10DDI_HRTCORELAYER hRTCoreLayer;
  union {
    const struct D3D11DDI_CORELAYER_DEVICECALLBACKS  *p11UMCallbacks;
  };
  UINT                  Flags;
} D3D11DDIARG_CREATEDEFERREDCONTEXT;
````


## -struct-fields




### -field hDrvContext

[in] A handle to the driver context for the driver-private handle storage. 


### -field hRTCoreLayer

[in] A handle that the driver should use when it calls back into the Direct3D runtime to access core Direct3D 11 functionality (that is, when the driver calls functions that the <b>p11UMCallbacks</b> member specifies). 


### -field Flags

[in] A valid bitwise OR of flag values that identify how to create a rendering device. The Direct3D runtime supports the following flags:  





#### D3D10DDI_CREATEDEVICE_FLAG_DISABLE_EXTRA_THREAD_CREATION (0x1)

If this flag is set, the user-mode display driver should not run multiple threads simultaneously when it processes calls to its functions from the Direct3D runtime. A driver can typically start and run multiple threads to process operations faster, unless D3D10DDI_CREATEDEVICE_FLAG_DISABLE_EXTRA_THREAD_CREATION is set.



#### D3D11DDI_CREATEDEVICE_FLAG_SINGLETHREADED (0x10)

This flag informs the user-mode display driver that the application is single threaded. The Direct3D version 11 runtime allows multiple application threads to enter the driver if the driver allows this mode of operation. However, not all applications can run multiple threads. If this flag is set, the driver will not expect multiple threads to enter it and run simultaneously. The driver can avoid synchronization if this flag is present.



#### The flag that is set in the 0xE mask of the Flags member

This flag represents the level of 3-D pipeline that the driver should support for the display device. The driver uses the following constant and macros to extract one of the values from the <a href="..\d3d10umddi\ne-d3d10umddi-d3d11ddi_3dpipelinelevel.md">D3D11DDI_3DPIPELINELEVEL</a> enumeration that represent the 3-D pipeline level to support. The value in the <b>Flags</b> member is formatted like the <b>Caps</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_3dpipelinesupport_caps.md">D3D11DDI_3DPIPELINESUPPORT_CAPS</a> structure.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_SHIFT (0x1)
#define D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_MASK (0x7 &lt;&lt; D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_SHIFT)
#define D3D11DDI_EXTRACT_3DPIPELINELEVEL_FROM_FLAGS( Flags ) \
    ((D3D11DDI_3DPIPELINELEVEL)(((Flags) &amp; D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_MASK) &gt;&gt; \
    D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_SHIFT))</pre>
</td>
</tr>
</table></span></div>

#### - p11ContextFuncs

[in/out] A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a> structure that the user-mode display driver fills with a table of its functions for the deferred context. The Direct3D runtime uses these functions to communicate with the user-mode display driver.

For a list of the functions that are not leveraged for deferred contexts, see <a href="https://msdn.microsoft.com/f6e7898a-7fb8-4a70-ab2e-3372a28db6f4">Excluding DDI Functions for Deferred Contexts</a>. 


#### - p11_1ContextFuncs

[in/out] A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_devicefuncs.md">D3D11_1DDI_DEVICEFUNCS</a> structure that the user-mode display driver fills with a table of its functions for the deferred context. The Direct3D runtime uses these functions to communicate with the user-mode display driver.

Supported starting with Windows 8.


#### - pWDDM1_3ContextFuncs

[in/out] A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm1_3ddi_devicefuncs.md">D3DWDDM1_3DDI_DEVICEFUNCS</a> structure that the user-mode display driver fills with a table of its functions for the deferred context. The Direct3D runtime uses these functions to communicate with the user-mode display driver.

Supported starting with Windows 8.1.


#### - p11UMCallbacks

[in] A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_corelayer_devicecallbacks.md">D3D11DDI_CORELAYER_DEVICECALLBACKS</a> structure that contains a table of Direct3D 11 runtime callback functions that the driver can use to access core user-mode runtime functionality. 


## -see-also

<a href="..\d3d10umddi\ne-d3d10umddi-d3d11ddi_3dpipelinelevel.md">D3D11DDI_3DPIPELINELEVEL</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_corelayer_devicecallbacks.md">D3D11DDI_CORELAYER_DEVICECALLBACKS</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_devicefuncs.md">D3D11_1DDI_DEVICEFUNCS</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_3dpipelinesupport_caps.md">D3D11DDI_3DPIPELINESUPPORT_CAPS</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11DDIARG_CREATEDEFERREDCONTEXT structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

