---
UID: NS:d3dumddi._D3DDDI_LOCKFLAGS
title: "_D3DDDI_LOCKFLAGS"
author: windows-driver-content
description: The D3DDDI_LOCKFLAGS structure identifies how to lock a resource.
old-location: display\d3dddi_lockflags.htm
tech.root: display
ms.assetid: b9bc6607-3222-45d0-a0d8-18c815a41771
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DDDI_LOCKFLAGS, D3DDDI_LOCKFLAGS structure [Display Devices], D3D_other_Structs_1bff30dd-936f-4753-bcbe-e656c454e675.xml, _D3DDDI_LOCKFLAGS, d3dumddi/D3DDDI_LOCKFLAGS, display.d3dddi_lockflags
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDI_LOCKFLAGS
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_LOCKFLAGS
---

# _D3DDDI_LOCKFLAGS structure


## -description


The D3DDDI_LOCKFLAGS structure identifies how to lock a resource.


## -struct-fields




### -field ReadOnly

A UINT value that specifies whether the locked resource can only be read from. Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field WriteOnly

A UINT value that specifies whether the locked resource can only be written to. Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field NoOverwrite

A UINT value that specifies whether the locked resource can have data appended to it but the existing data in the resource cannot be modified. This member is used only with Direct3D vertex buffer locks. 

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


### -field Discard

A UINT value that specifies whether the entire locked resource is modified. Therefore, because the existing contents can be discarded, they require no preliminary processing.

Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).


### -field RangeValid

A UINT value that specifies whether the locked resource is linear.

Setting this member is equivalent to setting the fifth bit of the 32-bit <b>Value</b> member (0x00000010).


### -field AreaValid

A UINT value that specifies whether the locked resource is a surface.

Setting this member is equivalent to setting the sixth bit of the 32-bit <b>Value</b> member (0x00000020).


### -field BoxValid

A UINT value that specifies whether the locked resource is a volume.

Setting this member is equivalent to setting the seventh bit of the 32-bit <b>Value</b> member (0x00000040).


### -field NotifyOnly

A UINT value that specifies whether the lock call is for notification only.

Setting this member is equivalent to setting the eighth bit of the 32-bit <b>Value</b> member (0x00000080).


### -field MightDrawFromLocked

A UINT value that specifies whether the driver is possibly requested to draw from a vertex buffer even if the vertex buffer is locked by the Direct3D runtime. <b>MightDrawFromLocked</b> does not guarantee that the driver will receive calls to its <a href="https://msdn.microsoft.com/12bb6274-d042-43bb-b9f5-1417f42da729">DrawIndexedPrimitive</a>, <a href="https://msdn.microsoft.com/f12af70c-a6f2-42da-be62-1cfeb90b6239">DrawIndexedPrimitive2</a>, <a href="https://msdn.microsoft.com/1a6de2b0-cab0-4fcf-be1b-a8cc1c1f79e9">DrawPrimitive</a>, and <a href="https://msdn.microsoft.com/a81080f0-fbb3-4616-9324-642b60befcb3">DrawPrimitive2</a> functions following the call to <b>Lock</b>. <b>MightDrawFromLocked</b> is set only on vertex buffers that were created with the <b>MightDrawFromLocked</b> bit-field flag set in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542963">D3DDDIARG_CREATERESOURCE</a> structure during create time.

Setting this member is equivalent to setting the ninth bit of the 32-bit <b>Value</b> member (0x00000100).


### -field DoNotWait

A UINT value that specifies whether the user-mode display driver should wait for the resource to become idle. Setting <b>DoNotWait</b> indicates that the user-mode display driver should not wait for the resource to become idle.

Setting this member is equivalent to setting the tenth bit of the 32-bit <b>Value</b> member (0x00000200).


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 22 bits (0xFFFFFC00) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A member in the union that is contained in D3DDDI_LOCKFLAGS that can hold one 32-bit value that identifies how to lock a resource.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543204">D3DDDIARG_LOCK</a>
 

 

