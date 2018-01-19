---
UID: NC:d3dkmddi.DXGKDDI_CREATECONTEXT
title: DXGKDDI_CREATECONTEXT
author: windows-driver-content
description: The DxgkDdiCreateContext function creates a graphics processing unit (GPU) context.
old-location: display\dxgkddicreatecontext.htm
old-project: display
ms.assetid: aea21a36-f3d5-4541-bd2d-aa026668c562
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiCreateContext
req.alt-loc: d3dkmddi.h
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
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_CREATECONTEXT callback



## -description
The <i>DxgkDdiCreateContext</i> function creates a graphics processing unit (GPU) context. 



## -prototype

````
DXGKDDI_CREATECONTEXT DxgkDdiCreateContext;

NTSTATUS APIENTRY DxgkDdiCreateContext(
  _In_    const HANDLE                hDevice,
  _Inout_       DXGKARG_CREATECONTEXT *pCreateContext
)
{ ... }
````


## -parameters

### -param hDevice [in]

[in] A handle to the graphics context device that the new context is created on. The display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <b>hDevice</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createdevice.md">DXGKARG_CREATEDEVICE</a> structure. 


### -param pCreateContext [in, out]

[in/out] A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createcontext.md">DXGKARG_CREATECONTEXT</a> structure that contains information about creating the context.


## -returns
<i>DxgkDdiCreateContext</i> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><i>DxgkDdiCreateContext</i> successfully created the context.
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl><i>DxgkDdiCreateContext</i> could not allocate memory that was required for it to complete.
<dl>
<dt><b>STATUS_GRAPHICS_DRIVER_MISMATCH</b></dt>
</dl>The display miniport driver is not compatible with the user-mode display driver that initiated the call to <i>DxgkDdiCreateContext</i>. 

 


## -remarks
A driver uses a GPU context to hold a collection of rendering state. 

A single process can create multiple contexts on a given device. 

The driver must support an arbitrary number of contexts. The only valid reason why a driver could not create a context is if system memory runs out. 

Typically, each context can reference any resource that was previously created for the device that owns that context. 

<i>DxgkDdiCreateContext</i> should be made pageable.


## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createcontext.md">DXGKARG_CREATECONTEXT</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createdevice.md">DXGKARG_CREATEDEVICE</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_CREATECONTEXT callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

