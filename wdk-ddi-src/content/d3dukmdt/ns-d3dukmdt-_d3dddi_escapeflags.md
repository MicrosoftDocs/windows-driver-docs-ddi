---
UID: NS:d3dukmdt._D3DDDI_ESCAPEFLAGS
title: "_D3DDDI_ESCAPEFLAGS"
author: windows-driver-content
description: The D3DDDI_ESCAPEFLAGS structure identifies how the user-mode display driver shares information with the display miniport driver.
old-location: display\d3dddi_escapeflags.htm
tech.root: display
ms.assetid: 40648f6a-3393-4374-beff-e097c299f9e9
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DDDI_ESCAPEFLAGS, D3DDDI_ESCAPEFLAGS structure [Display Devices], D3D_other_Structs_5ff9ad07-6a44-4a53-a70c-5abdbe84065a.xml, _D3DDDI_ESCAPEFLAGS, d3dukmdt/D3DDDI_ESCAPEFLAGS, display.d3dddi_escapeflags
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating system.
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
-	d3dukmdt.h
api_name:
-	D3DDDI_ESCAPEFLAGS
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_ESCAPEFLAGS
---

# _D3DDDI_ESCAPEFLAGS structure


## -description


The D3DDDI_ESCAPEFLAGS structure identifies how the user-mode display driver shares information with the display miniport driver.


## -struct-fields




### -field HardwareAccess

A <b>UINT</b> value that specifies whether the operating system performs the <a href="https://msdn.microsoft.com/2b7c1eae-6527-469e-a2fa-74d2a1246bd3">second level of synchronization</a> into the display miniport driver for the <a href="https://msdn.microsoft.com/79a524cd-dec1-4ea8-a660-d9d9c644e162">DxgkDdiEscape</a> call. If the driver requires the second level of synchronization and the <b>HardwareAccess</b> flag is not set, the call to the driver's <i>DxgkDdiEscape</i> function should fail. 

Starting in Windows 8.1,  if this member is set, <b>DeviceStatusQuery</b> and <b>ChangeFrameLatency</b> must be set to zero.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field DeviceStatusQuery


  
  If set, when the <a href="https://msdn.microsoft.com/66c0347f-2cf3-42fc-8641-47c731e958c9">pfnEscapeCb</a> function is called and the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544190">D3DDDICB_ESCAPE</a>.<b>PrivateDriverDataSize</b> member is <code>sizeof(D3DDDI_EXECUTIONSTATEESCAPE)</code>, the Direct3D runtime interprets the <b>D3DDDICB_ESCAPE</b>.<b>pPrivateDriverData</b> member as a pointer to a buffer that contains a <a href="https://msdn.microsoft.com/library/windows/hardware/dn482417">D3DDDI_EXECUTIONSTATEESCAPE</a> structure. In addition, the runtime processes the <i>pfnEscapeCb</i> as a status query by writing the requested info into the provided buffer instead of sending a <a href="https://msdn.microsoft.com/79a524cd-dec1-4ea8-a660-d9d9c644e162">DxgkDdiEscape</a> call to the display miniport driver.

If this member is set, <b>HardwareAccess</b> and <b>ChangeFrameLatency</b> must be set to zero.

Supported starting with Windows 8.1.

The operating system ignores this member if it is prior to Windows 8.1, or if the user-mode driver was initialized with an <i>OpenAdapterXxx</i> call where the <i>pOpenData</i>-&gt;<b>Interface</b> member indicates Direct3D version 8 or earlier.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field ChangeFrameLatency


  
  If set, when the <a href="https://msdn.microsoft.com/66c0347f-2cf3-42fc-8641-47c731e958c9">pfnEscapeCb</a> function is called, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544190">D3DDDICB_ESCAPE</a>.<b>PrivateDriverDataSize</b> member is <code>sizeof(D3DDDI_FRAMELATENCYESCAPE)</code> and conditions in Remarks are also met, the Direct3D runtime interprets the <b>D3DDDICB_ESCAPE</b>.<b>pPrivateDriverData</b> member as a pointer to a buffer that contains a <a href="https://msdn.microsoft.com/library/windows/hardware/dn482418">D3DDDI_FRAMELATENCYESCAPE</a> structure. In addition, the runtime processes the <i>pfnEscapeCb</i> as a request to change the DirectX graphics kernel subsystem's maximum frame latency by writing the requested info into the provided buffer instead of sending a <a href="https://msdn.microsoft.com/79a524cd-dec1-4ea8-a660-d9d9c644e162">DxgkDdiEscape</a> call to the display miniport driver.

If this member is set, <b>HardwareAccess</b> and <b>DeviceStatusQuery</b> must be set to zero.

Supported starting with Windows 8.1.

The operating system ignores this member if it is prior to Windows 8.1, or if the user-mode driver was initialized with an <i>OpenAdapterXxx</i> call where the <i>pOpenData</i>-&gt;<b>Interface</b> member indicates Direct3D version 8 or earlier.

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


### -field NoAdapterSynchronization




### -field VirtualMachineData

Indicates that [DxgkDdiEscape](..\d3dkmddi\nc-d3dkmddi-dxgkddi_escape.md) is called from a virtual machine.


### -field Reserved2

This member is reserved and should be set to zero.

### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 29 bits (0xFFFFFFF8) of the 32-bit <b>Value</b> member to zeros.

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A member in the union that is contained in D3DDDI_ESCAPEFLAGS that can hold one 32-bit value that identifies how to share information.


## -remarks



If <b>ChangeFrameLatency</b> is set, a <a href="https://msdn.microsoft.com/66c0347f-2cf3-42fc-8641-47c731e958c9">pfnEscapeCb</a> call will succeed only if:

<ul>
<li>The display miniport driver is responsible for a linked adapter configuration (LDA) provided by a single vendor.</li>
<li>The app has taken exclusive full-screen ownership of the display at some point in its lifetime.</li>
<li>The app has not overridden the default maximum frame latency value of 3.</li>
</ul>
If these conditions are not met, <i>pfnEscapeCb</i> call returns an <b>E_INVALIDARG</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544190">D3DDDICB_ESCAPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn482417">D3DDDI_EXECUTIONSTATEESCAPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn482418">D3DDDI_FRAMELATENCYESCAPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557588">DXGKARG_ESCAPE</a>



<a href="https://msdn.microsoft.com/79a524cd-dec1-4ea8-a660-d9d9c644e162">DxgkDdiEscape</a>



<a href="https://msdn.microsoft.com/66c0347f-2cf3-42fc-8641-47c731e958c9">pfnEscapeCb</a>
 

 

