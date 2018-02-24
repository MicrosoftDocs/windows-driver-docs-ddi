---
UID: NS:d3dkmddi._DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS
title: "_DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS"
author: windows-driver-content
description: The DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS structure indicates whether the display miniport driver provides a physical adapter mask in a call to the DxgkCbNotifyInterrupt function.
old-location: display\dxgkcb_notify_interrupt_data_flags.htm
old-project: display
ms.assetid: 69554ec0-3d5e-4a53-8b45-2f821ddbfd3c
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.dxgkcb_notify_interrupt_data_flags, DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS, _DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS, DmStructs_bfff264e-44a2-458c-ab0d-c103d4b76f71.xml, DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS structure [Display Devices], d3dkmddi/DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS
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
-	DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS
product: Windows
targetos: Windows
req.typenames: DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS
---

# _DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS structure


## -description


The DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS structure indicates whether the display miniport driver provides a physical adapter mask in a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a> function.


## -syntax


````
typedef struct _DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS {
  union {
    struct {
      UINT ValidPhysicalAdapterMask  :1;
      UINT HsyncFlipCompletion  :1;
      UINT Reserved  :30;
    };
    UINT Value;
  };
} DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS;
````


## -struct-fields




### -field ValidPhysicalAdapterMask

A UINT value that specifies whether the driver provides a physical adapter mask. If this member is set, the driver provides a physical adapter mask in the <b>PhysicalAdapterMask</b> member of the <b>CrtcVsync</b> structure that is contained in the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a> structure. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field HsyncFlipCompletion

A UINT value that specifies whether the Hsync flip has been completed.


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.


#### - Value

A member in the union that DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS contains that can hold a 32-bit value.


## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

