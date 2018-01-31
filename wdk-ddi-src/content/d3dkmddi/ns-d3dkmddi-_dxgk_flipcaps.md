---
UID: NS:d3dkmddi._DXGK_FLIPCAPS
title: "_DXGK_FLIPCAPS"
author: windows-driver-content
description: The DXGK_FLIPCAPS structure identifies flipping capabilities of the display miniport driver that the driver provides through a call to its DxgkDdiQueryAdapterInfo function.
old-location: display\dxgk_flipcaps.htm
old-project: display
ms.assetid: 33399b7c-ce67-4c49-be26-2b2d759ff5a0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmddi/DXGK_FLIPCAPS, display.dxgk_flipcaps, DXGK_FLIPCAPS, DmStructs_11bba63e-8001-41d2-9c60-978024921994.xml, DXGK_FLIPCAPS structure [Display Devices], _DXGK_FLIPCAPS
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
-	DXGK_FLIPCAPS
product: Windows
targetos: Windows
req.typenames: DXGK_FLIPCAPS
---

# _DXGK_FLIPCAPS structure


## -description


The <b>DXGK_FLIPCAPS</b> structure identifies flipping capabilities of the display miniport driver that the driver provides through a call to its <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> function.


## -syntax


````
typedef struct _DXGK_FLIPCAPS {
  union {
    struct {
      UINT FlipOnVSyncWithNoWait  :1;
      UINT FlipOnVSyncMmIo  :1;
      UINT FlipInterval  :1;
      UINT FlipImmediateMmIo  :1;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3)
      UINT FlipIndependent  :1;
      UINT Reserved  :27;
#endif 
      UINT Reserved  :28;
    };
    UINT Value;
  };
} DXGK_FLIPCAPS;
````


## -struct-fields




#### - FlipOnVSyncWithNoWait

A <b>UINT</b> value that specifies whether the driver supports the scheduling of a flip command that will take effect on the next vertical retrace period (vertical sync) without causing the graphics pipeline to stall until that vertical sync occurs. That is, the graphics pipeline must proceed immediately after the driver writes the physical address of the flipping surface into flip-pending registers at the hardware. Although most hardware uses a depth of one flip-pending register, if hardware uses more than one flip-pending register, the driver should specify the number in the <b>MaxQueuedFlipOnVSync</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a> structure. 

If <b>FlipOnVSyncWithNoWait</b> is set to 1 (<b>TRUE</b>), the driver supports this mechanism. If <b>FlipOnVSyncWithNoWait</b> is set to 0 (<b>FALSE</b>), the driver does not support this mechanism. That is, the graphics pipeline must wait until the next vertical sync occurs after the scheduling of a flip command to take effect on the next vertical sync.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


#### - FlipOnVSyncMmIo

A <b>UINT</b> value that specifies whether the driver supports a memory mapped I/O (MMIO)-based flip that takes effect on the next vertical sync. To support this type of flip, the display miniport driver must support the following operations:
<ul>
<li>
No generation of a DMA buffer to pass in a call to its <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_present.md">DxgkDdiPresent</a> function (that is, <b>NULL</b> is passed in the <b>pDmaBuffer</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_present.md">DXGKARG_PRESENT</a> structure).

</li>
<li>
A flip through a call to its <a href="https://msdn.microsoft.com/488c929b-3816-457f-b5c2-c176b93d5546">DxgkDdiSetVidPnSourceAddress</a> function at device interrupt request level (DIRQL). In the call to <i>DxgkDdiSetVidPnSourceAddress</i>, the driver should program the digital-to-analog converter (DAC) and use the value in the <b>PrimaryAddress</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_setvidpnsourceaddress.md">DXGKARG_SETVIDPNSOURCEADDRESS</a> structure to start the scan out. After the vertical sync, the driver should notify the GPU scheduler to report the effective scan address by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a> function with the <b>DXGK_INTERRUPT_CRTC_VSYNC</b> value set in the <b>InterruptType</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a> structure. The driver should then call the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_dpc.md">DxgkCbNotifyDpc</a> function to perform most of the scan-out processing.

</li>
</ul>

#### - FlipInterval

A <b>UINT</b> value that specifies whether the driver supports the scheduling of a flip command to take effect after two, three, or four vertical syncs occur. Regardless of whether the driver supports a flip interval of two or greater, the driver must support an immediate flip and a flip interval of one.

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


#### - FlipImmediateMmIo

A <b>UINT</b> value that specifies whether the driver supports a memory mapped I/O (MMIO)-based immediate flip. This type of flip takes effect immediately following a call to the driver's <a href="https://msdn.microsoft.com/488c929b-3816-457f-b5c2-c176b93d5546">DxgkDdiSetVidPnSourceAddress</a> function without waiting for the next vertical sync to occur.

Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).

Supported starting with Windows 7.


#### - FlipIndependent

A <b>UINT</b> value that specifies whether the driver supports an independent flip. WDDM 1.3 and later drivers must set this member to 1.

In an <i>independent flip</i>, the operating system attempts to bypass a Desktop Window Manager (DWM) user-mode present call and flips to the application back buffer by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_present.md">DxgkDdiPresent</a>  and <a href="https://msdn.microsoft.com/488c929b-3816-457f-b5c2-c176b93d5546">DxgkDdiSetVidPnSourceAddress</a> in Direct Flip and multiplane overlay presentation models.

Note that there will be cases when a DWM user-mode present call is made even when <b>FlipIndependent</b> is set. Your driver must still handle such cases.

Setting this member is equivalent to setting the fifth bit of the 32-bit <b>Value</b> member (0x00000010).

Supported starting with Windows 8.1.


### -field DdiPresentForIFlip

 


### -field FlipImmediateOnHSync

 


#### - Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 27 bits (0xFFFFFFE0) of the 32-bit <b>Value</b> member to zeros.

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 28 bits (0xFFFFFFF0) of the 32-bit <b>Value</b> member to zeros.


#### - Value

A member in the union that DXGK_FLIPCAPS contains that can hold a 32-bit value that identifies flipping capabilities.


## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_present.md">DxgkDdiPresent</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_setvidpnsourceaddress.md">DXGKARG_SETVIDPNSOURCEADDRESS</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_dpc.md">DxgkCbNotifyDpc</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_present.md">DXGKARG_PRESENT</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a>

<a href="https://msdn.microsoft.com/488c929b-3816-457f-b5c2-c176b93d5546">DxgkDdiSetVidPnSourceAddress</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_FLIPCAPS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

