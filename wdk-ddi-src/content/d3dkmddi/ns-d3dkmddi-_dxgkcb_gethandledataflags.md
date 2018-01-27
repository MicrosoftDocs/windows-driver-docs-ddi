---
UID: NS:d3dkmddi._DXGKCB_GETHANDLEDATAFLAGS
title: _DXGKCB_GETHANDLEDATAFLAGS
author: windows-driver-content
description: The DXGKCB_GETHANDLEDATAFLAGS structure indicates if allocations belong to a resource.
old-location: display\dxgkcb_gethandledataflags.htm
old-project: display
ms.assetid: 01689a2f-115a-4db8-b53d-38717c10a0ff
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DmStructs_a0288df8-0513-4823-9445-cd86ff45a186.xml, DXGKCB_GETHANDLEDATAFLAGS, DXGKCB_GETHANDLEDATAFLAGS structure [Display Devices], d3dkmddi/DXGKCB_GETHANDLEDATAFLAGS, display.dxgkcb_gethandledataflags, _DXGKCB_GETHANDLEDATAFLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	d3dkmddi.h
apiname: 
-	DXGKCB_GETHANDLEDATAFLAGS
product: Windows
targetos: Windows
req.typenames: DXGKCB_GETHANDLEDATAFLAGS
---

# _DXGKCB_GETHANDLEDATAFLAGS structure


## -description


The DXGKCB_GETHANDLEDATAFLAGS structure indicates if allocations belong to a resource.


## -syntax


````
typedef struct _DXGKCB_GETHANDLEDATAFLAGS {
  union {
    struct {
      UINT DeviceSpecific  :1;
      UINT Reserved  :31;
    };
    UINT Value;
  };
} DXGKCB_GETHANDLEDATAFLAGS;
````


## -struct-fields




### -field DeviceSpecific

A UINT value that specifies whether allocations belong to a resource. If this member is set, the allocations belong to a resource. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A member in the union that DXGKCB_GETHANDLEDATAFLAGS contains that can hold a 32-bit value that indicates if allocations belong to a resource.


## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_gethandledata.md">DXGKARGCB_GETHANDLEDATA</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_GETHANDLEDATAFLAGS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

