---
UID: NC:d3dkmddi.DXGKDDI_DESTROYCONTEXT
title: DXGKDDI_DESTROYCONTEXT
author: windows-driver-content
description: The DxgkDdiDestroyContext function destroys the specified graphics processing unit (GPU) context.
old-location: display\dxgkddidestroycontext.htm
old-project: display
ms.assetid: c21f62ab-c52e-43a2-a3a1-6fd6e5fbde01
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
req.alt-api: DxgkDdiDestroyContext
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

# DXGKDDI_DESTROYCONTEXT callback



## -description
The <i>DxgkDdiDestroyContext</i> function destroys the specified graphics processing unit (GPU) context.



## -prototype

````
DXGKDDI_DESTROYCONTEXT DxgkDdiDestroyContext;

NTSTATUS APIENTRY DxgkDdiDestroyContext(
  _In_ const HANDLE hContext
)
{ ... }
````


## -parameters

### -param hContext [in]

[in] A handle to the context to destroy. The display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a> function previously returned this handle in the <b>hContext</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createcontext.md">DXGKARG_CREATECONTEXT</a> structure that the <i>pCreateContext</i> parameter of <i>DxgkDdiCreateContext </i>points to. 


## -returns
<i>DxgkDdiDestroyContext</i> returns STATUS_SUCCESS, or an appropriate error result if the context is not successfully destroyed.


## -remarks
A driver should free all resources that it allocated for the context and clean up any internal tracking data structures.

<i>DxgkDdiDestroyContext</i> should be made pageable.


## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createcontext.md">DXGKARG_CREATECONTEXT</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_DESTROYCONTEXT callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

