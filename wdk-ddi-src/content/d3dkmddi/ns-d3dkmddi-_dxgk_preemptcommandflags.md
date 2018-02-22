---
UID: NS:d3dkmddi._DXGK_PREEMPTCOMMANDFLAGS
title: "_DXGK_PREEMPTCOMMANDFLAGS"
author: windows-driver-content
description: The DXGK_PREEMPTCOMMANDFLAGS structure specifies a union that contains either a structure with a reserved member or a 32-bit value. No bit-field flags are currently defined.
old-location: display\dxgk_preemptcommandflags.htm
old-project: display
ms.assetid: 24444451-7323-4e1a-9981-cf5caa00c4e3
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: d3dkmddi/DXGK_PREEMPTCOMMANDFLAGS, _DXGK_PREEMPTCOMMANDFLAGS, DXGK_PREEMPTCOMMANDFLAGS structure [Display Devices], display.dxgk_preemptcommandflags, DmStructs_7163ce37-49c8-4b17-aadc-cd36ad5cac9d.xml, DXGK_PREEMPTCOMMANDFLAGS
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
-	DXGK_PREEMPTCOMMANDFLAGS
product: Windows
targetos: Windows
req.typenames: DXGK_PREEMPTCOMMANDFLAGS
---

# _DXGK_PREEMPTCOMMANDFLAGS structure


## -description


The DXGK_PREEMPTCOMMANDFLAGS structure specifies a union that contains either a structure with a reserved member or a 32-bit value. No bit-field flags are currently defined.


## -syntax


````
typedef struct _DXGK_PREEMPTCOMMANDFLAGS {
  union {
    struct {
      UINT Reserved  :32;
    };
    UINT Value;
  };
} DXGK_PREEMPTCOMMANDFLAGS;
````


## -struct-fields




### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting all 32 bits (0xFFFFFFFF) of the 32-bit <b>Value</b> member to zeros.


#### - Value

A member in the union that DXGK_PREEMPTCOMMANDFLAGS contains that can hold a 32-bit value.


## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_preemptcommand.md">DXGKARG_PREEMPTCOMMAND</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_PREEMPTCOMMANDFLAGS structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

