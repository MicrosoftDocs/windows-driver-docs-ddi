---
UID: NS:d3dumddi._D3DDDIARG_RECLAIMRESOURCES
title: _D3DDDIARG_RECLAIMRESOURCES
author: windows-driver-content
description: Describes video memory resources that are to be reclaimed and that the user-mode display driver previously offered for reuse. Used with the ReclaimResources function.
old-location: display\d3dddiarg_reclaimresources.htm
old-project: display
ms.assetid: 58e8738c-b10a-4c93-b179-03efcb65412d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DDDIARG_RECLAIMRESOURCES, D3DDDIARG_RECLAIMRESOURCES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_RECLAIMRESOURCES
req.alt-loc: D3dumddi.h
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
req.typenames: D3DDDIARG_RECLAIMRESOURCES
---

# _D3DDDIARG_RECLAIMRESOURCES structure



## -description
Describes video memory resources that are to be reclaimed and that the user-mode display driver  previously offered  for reuse. Used with the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_reclaimresources.md">ReclaimResources</a> function.



## -syntax

````
typedef struct _D3DDDIARG_RECLAIMRESOURCES {
  HANDLE *pResources;
  BOOL   *pDiscarded;
  UINT   Resources;
} D3DDDIARG_RECLAIMRESOURCES;
````


## -struct-fields

### -field pResources

[in] A pointer to an array of handles to the resources that are to be reclaimed.


### -field pDiscarded

[out] An optional array of Boolean values that specify whether each resource or allocation was discarded.

Each Boolean value in this array corresponds to a resource at the same index location in the structure pointed to by <b>pResources</b>.

The driver sets each Boolean value to <b>TRUE</b> if the corresponding resource was discarded, or to <b>FALSE</b> if not.

If <b>pDiscarded</b> is <b>NULL</b>, the driver can ignore it.


### -field Resources

[in] The number of elements in the arrays pointed to by <b>pResources</b> and <b>pDiscarded</b>.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_reclaimresources.md">ReclaimResources</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_RECLAIMRESOURCES structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

