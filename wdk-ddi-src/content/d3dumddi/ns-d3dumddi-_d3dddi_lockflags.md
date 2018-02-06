---
UID: NS:d3dumddi._D3DDDI_LOCKFLAGS
title: "_D3DDDI_LOCKFLAGS"
author: windows-driver-content
description: The D3DDDI_LOCKFLAGS structure identifies how to lock a resource.
old-location: display\d3dddi_lockflags.htm
old-project: display
ms.assetid: b9bc6607-3222-45d0-a0d8-18c815a41771
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dddi_lockflags, d3dumddi/D3DDDI_LOCKFLAGS, _D3DDDI_LOCKFLAGS, D3DDDI_LOCKFLAGS, D3D_other_Structs_1bff30dd-936f-4753-bcbe-e656c454e675.xml, D3DDDI_LOCKFLAGS structure [Display Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDI_LOCKFLAGS
product: Windows
targetos: Windows
req.typenames: D3DDDI_LOCKFLAGS
---

# _D3DDDI_LOCKFLAGS structure


## -description


The D3DDDI_LOCKFLAGS structure identifies how to lock a resource.


## -syntax


````
typedef struct _D3DDDI_LOCKFLAGS {
  union {
    struct {
      UINT ReadOnly  :1;
      UINT WriteOnly  :1;
      UINT NoOverwrite  :1;
      UINT Discard  :1;
      UINT RangeValid  :1;
      UINT AreaValid  :1;
      UINT BoxValid  :1;
      UINT NotifyOnly  :1;
      UINT MightDrawFromLocked  :1;
      UINT DoNotWait  :1;
      UINT Reserved  :22;
    };
    UINT   Value;
  };
} D3DDDI_LOCKFLAGS;
````


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

A UINT value that specifies whether the driver is possibly requested to draw from a vertex buffer even if the vertex buffer is locked by the Direct3D runtime. <b>MightDrawFromLocked</b> does not guarantee that the driver will receive calls to its <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawindexedprimitive.md">DrawIndexedPrimitive</a>, <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawindexedprimitive2.md">DrawIndexedPrimitive2</a>, <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawprimitive.md">DrawPrimitive</a>, and <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawprimitive2.md">DrawPrimitive2</a> functions following the call to <b>Lock</b>. <b>MightDrawFromLocked</b> is set only on vertex buffers that were created with the <b>MightDrawFromLocked</b> bit-field flag set in the <b>Flags</b> member of the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddiarg_createresource.md">D3DDDIARG_CREATERESOURCE</a> structure during create time.

Setting this member is equivalent to setting the ninth bit of the 32-bit <b>Value</b> member (0x00000100).


### -field DoNotWait

A UINT value that specifies whether the user-mode display driver should wait for the resource to become idle. Setting <b>DoNotWait</b> indicates that the user-mode display driver should not wait for the resource to become idle.

Setting this member is equivalent to setting the tenth bit of the 32-bit <b>Value</b> member (0x00000200).


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 22 bits (0xFFFFFC00) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A member in the union that is contained in D3DDDI_LOCKFLAGS that can hold one 32-bit value that identifies how to lock a resource.


## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_lock.md">D3DDDIARG_LOCK</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_LOCKFLAGS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

