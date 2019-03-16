---
UID: NS:d3dkmddi._DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS
title: _DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS (d3dkmddi.h)
description: The DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS structure indicates whether the display miniport driver provides a physical adapter mask in a call to the DxgkCbNotifyInterrupt function.
old-location: display\dxgkcb_notify_interrupt_data_flags.htm
ms.assetid: 69554ec0-3d5e-4a53-8b45-2f821ddbfd3c
ms.date: 05/10/2018
ms.keywords: DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS, DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS structure [Display Devices], DmStructs_bfff264e-44a2-458c-ab0d-c103d4b76f71.xml, _DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS, d3dkmddi/DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS, display.dxgkcb_notify_interrupt_data_flags
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS
---

# _DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS structure


## -description


The DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS structure indicates whether the display miniport driver provides a physical adapter mask in a call to the <a href="https://msdn.microsoft.com/7968d26d-0195-463d-8954-e7ebef4f9dea">DxgkCbNotifyInterrupt</a> function.


## -struct-fields




### -field ValidPhysicalAdapterMask

A UINT value that specifies whether the driver provides a physical adapter mask. If this member is set, the driver provides a physical adapter mask in the <b>PhysicalAdapterMask</b> member of the <b>CrtcVsync</b> structure that is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557538">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a> structure. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field HsyncFlipCompletion

A UINT value that specifies whether the Hsync flip has been completed.


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A member in the union that DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS contains that can hold a 32-bit value.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557538">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a>



<a href="https://msdn.microsoft.com/7968d26d-0195-463d-8954-e7ebef4f9dea">DxgkCbNotifyInterrupt</a>
 

 

