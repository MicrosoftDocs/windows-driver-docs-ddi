---
UID: NS:d3dumddi._D3DDDI_LOCKASYNCFLAGS
title: "_D3DDDI_LOCKASYNCFLAGS"
author: windows-driver-content
description: The D3DDDI_LOCKASYNCFLAGS structure identifies how to lock a resource.
old-location: display\d3dddi_lockasyncflags.htm
old-project: display
ms.assetid: 0e6dd14c-5192-4c4b-9dcb-716989d24588
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: D3D_other_Structs_765c2b3d-14e2-4eaf-978f-764263aa2a99.xml, _D3DDDI_LOCKASYNCFLAGS, display.d3dddi_lockasyncflags, D3DDDI_LOCKASYNCFLAGS structure [Display Devices], D3DDDI_LOCKASYNCFLAGS, d3dumddi/D3DDDI_LOCKASYNCFLAGS
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
-	D3DDDI_LOCKASYNCFLAGS
product: Windows
targetos: Windows
req.typenames: D3DDDI_LOCKASYNCFLAGS
---

# _D3DDDI_LOCKASYNCFLAGS structure


## -description


The D3DDDI_LOCKASYNCFLAGS structure identifies how to lock a resource.


## -syntax


````
typedef struct _D3DDDI_LOCKASYNCFLAGS {
  union {
    struct {
      UINT NoOverwrite  :1;
      UINT Discard  :1;
      UINT RangeValid  :1;
      UINT AreaValid  :1;
      UINT BoxValid  :1;
      UINT NoExistingReferences  :1;
      UINT NotifyOnly  :1;
      UINT Reserved  :25;
    };
    UINT   Value;
  };
} D3DDDI_LOCKASYNCFLAGS;
````


## -struct-fields




### -field NoOverwrite

A UINT value that specifies whether the locked resource can have data appended to it but the existing data in the resource cannot be modified. This member is used only with Microsoft Direct3D vertex buffer locks. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Discard

A UINT value that specifies whether the entire locked resource is modified. If this value is set, because the existing contents can be discarded, the contents require no preliminary processing.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field RangeValid

A UINT value that specifies whether the locked resource is linear.

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


### -field AreaValid

A UINT value that specifies whether the locked resource is a surface.

Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).


### -field BoxValid

A UINT value that specifies whether the locked resource is a volume.

Setting this member is equivalent to setting the fifth bit of the 32-bit <b>Value</b> member (0x00000010).


### -field NoExistingReferences

A UINT value that specifies whether the Microsoft Direct3D runtime has any queued references to the resource to be locked. If <b>NoExistingReferences</b> is set, the driver determines that no internally queued references to the resource are available. The driver can then set the <b>NoExistingReferences</b> bit-field flag of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_lock.md">D3DDDICB_LOCK</a> structure when the driver calls the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a> function to perform a lock-discard operation. 

Setting this member is equivalent to setting the sixth bit of the 32-bit <b>Value</b> member (0x00000020).


### -field NotifyOnly

A UINT value that specifies whether the lock call is for notification only. The Direct3D runtime sets <b>NotifyOnly</b> to <b>TRUE</b> when it locks runtime-allocated system memory surfaces. In this situation, the runtime ignores the pointer that the driver returns in the <b>pSurfData</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_lockasync.md">D3DDDIARG_LOCKASYNC</a> structure.

Setting this member is equivalent to setting the seventh bit of the 32-bit <b>Value</b> member (0x00000040).


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 25 bits (0xFFFFFF80) of the 32-bit <b>Value</b> member to zeros.


#### - Value

A member in the union that is contained in D3DDDI_LOCKASYNCFLAGS that can hold one 32-bit value that identifies how to lock a resource.


## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_lockasync.md">D3DDDIARG_LOCKASYNC</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_LOCKASYNCFLAGS structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

