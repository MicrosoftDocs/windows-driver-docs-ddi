---
UID: NS:d3dumddi._D3DDDIARG_QUERYRESOURCERESIDENCY
title: _D3DDDIARG_QUERYRESOURCERESIDENCY
author: windows-driver-content
description: The D3DDDIARG_QUERYRESOURCERESIDENCY structure describes a list of resources on which residency is verified through the QueryResourceResidency function.
old-location: display\d3dddiarg_queryresourceresidency.htm
old-project: display
ms.assetid: 14c0cb12-3ed0-4c78-befa-6da9e8cd7dbc
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DDDIARG_QUERYRESOURCERESIDENCY, D3DDDIARG_QUERYRESOURCERESIDENCY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_QUERYRESOURCERESIDENCY
req.alt-loc: d3dumddi.h
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
req.typenames: D3DDDIARG_QUERYRESOURCERESIDENCY
---

# _D3DDDIARG_QUERYRESOURCERESIDENCY structure



## -description
The D3DDDIARG_QUERYRESOURCERESIDENCY structure describes a list of resources on which residency is verified through the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryresourceresidency.md">QueryResourceResidency</a> function. 



## -syntax

````
typedef struct _D3DDDIARG_QUERYRESOURCERESIDENCY {
  const HANDLE *pHandleList;
  UINT         NumResources;
} D3DDDIARG_QUERYRESOURCERESIDENCY;
````


## -struct-fields

### -field pHandleList

[in] An array of handles to resources whose residency is queried. <b>pHandleList</b> cannot be <b>NULL</b>. A resource can be an object, which is derived from the <b>IDirect3DResource9</b> interface for a texture, volume texture, cube texture, vertex buffer, index buffer, or surface. For more information about <b>IDirect3DResource9</b>, see the DirectX SDK documentation.


### -field NumResources

[in] The number of resources in the array in the <b>pHandleList</b> member. The range is from 1 through 0xFFFFF.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryresourceresidency.md">QueryResourceResidency</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_QUERYRESOURCERESIDENCY structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

