---
UID: NS:d3dkmddi._DXGK_VIDSCHCAPS
title: "_DXGK_VIDSCHCAPS"
author: windows-driver-content
description: The DXGK_VIDSCHCAPS structure identifies the graphics processing unit (GPU) scheduling capabilities, in bit-field flags, that a driver can support.
old-location: display\dxgk_vidschcaps.htm
tech.root: display
ms.assetid: 714741b5-aec1-4d79-8199-00e8d97e6637
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DXGK_VIDSCHCAPS, DXGK_VIDSCHCAPS structure [Display Devices], DmStructs_01f721e4-8585-46b1-a911-9fa904a29f7e.xml, _DXGK_VIDSCHCAPS, d3dkmddi/DXGK_VIDSCHCAPS, display.dxgk_vidschcaps
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available beginning with Windows Vista.
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
-	d3dkmddi.h
api_name:
-	DXGK_VIDSCHCAPS
product:
- Windows
targetos: Windows
req.typenames: DXGK_VIDSCHCAPS
---

# _DXGK_VIDSCHCAPS structure


## -description


The DXGK_VIDSCHCAPS structure identifies the graphics processing unit (GPU) scheduling capabilities, in bit-field flags, that a driver can support.


## -struct-fields




### -field MultiEngineAware

A UINT value that specifies whether the driver supports the creation and destruction of a device context (through the <a href="https://msdn.microsoft.com/aea21a36-f3d5-4541-bd2d-aa026668c562">DxgkDdiCreateContext</a> and <a href="https://msdn.microsoft.com/c21f62ab-c52e-43a2-a3a1-6fd6e5fbde01">DxgkDdiDestroyContext</a> functions) and the use of a device context (through the <a href="https://msdn.microsoft.com/1a46b129-1e78-44e6-a609-59eab206692b">DxgkDdiPresent</a> and <a href="https://msdn.microsoft.com/fd634768-5e1e-4f40-82fd-5ef69148c3d7">DxgkDdiRender</a> functions). If the driver does not support context creation, for every call to the driver that would pass a handle to a context, the Microsoft DirectX graphics kernel subsystem replaces the handle to the context with a handle to the device.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field VSyncPowerSaveAware

A UINT value that specifies whether the driver supports vertical-sync power-saving functionality. 
        

If <b>VSyncPowerSaveAware</b> is set to 1 (<b>TRUE</b>), the operating system can save power by disabling and enabling the vertical-sync interrupt that occurs from the usage of some applications. If <b>VSyncPowerSaveAware</b> is set to zero (<b>FALSE</b>), the operating system will never disable the vertical-sync interrupt for applications that might cause the vertical-sync interrupt to occur.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).

Supported starting with Windows Server 2008 and Windows Vista with SP1.


### -field PreemptionAware

A UINT value that specifies whether the driver supports the   GPU preemption policy of Windows 8 and later versions of Windows. With this policy, the operating system always issues preemption requests to the GPU before it initiates the <a href="https://msdn.microsoft.com/f410eec7-026f-41e0-8c60-72f651659ead">Timeout Detection and Recovery
(TDR)</a> process.
        

If <b>PreemptionAware</b> is set to 1 (<b>TRUE</b>), the driver supports the preemption policy of Windows 8 and later versions of Windows.

If <b>PreemptionAware</b> is set to zero (<b>FALSE</b>), the driver supports the preemption policy  of Windows 7. With this policy, the operating system may not issue preemption requests while potentially long running operations are being executed on the GPU. As a result, these GPU requests are not preempted  before the TDR process is initiated. This may cause the TDR process to repeatedly reset the GPU which could lead to a system stop error.

<div class="alert"><b>Note</b>  If <b>PreemptionAware</b> is set to 1, the <b>MultiEngineAware</b> member  must also be set to a value of 1. If <b>PreemptionAware</b> is set to 1 but <b>MultiEngineAware</b> is set to zero, the operating system will halt the driver initialization process and return a failure code.</div>
<div> </div>
Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).

Supported starting with Windows 8.


### -field NoDmaPatching

A UINT value that specifies whether the driver disables leak detection for DMA buffers that are split into multiple parts. This detection is performed after the driver's <a href="https://msdn.microsoft.com/363be784-0e3b-4f9a-a643-80857478bbae">DxgkDdiPatch</a> function is called to assign, or <i>patch</i>, physical addresses to each part of the DMA buffer.

<div class="alert"><b>Note</b>  Display devices that support virtual addresses can reprogram a virtual address to a new video memory location without having to patch the value of the DMA buffer address. For these types of display devices, the driver should set <b>NoDmaPatching</b> to 1.</div>
<div> </div>
If <b>NoDmaPatching</b> is set to 1 (<b>TRUE</b>), the driver disables leak detection, and the behavior of DMA buffer splitting is the same as in Windows 7.

If <b>NoDmaPatching</b> is set to 0 (<b>FALSE</b>), the driver enables leak detection for patched DMA buffer addresses. The operating system performs leak detection before it calls the driver's <a href="https://msdn.microsoft.com/363be784-0e3b-4f9a-a643-80857478bbae">DxgkDdiPatch</a> function.

<div class="alert"><b>Note</b>  If <b>NoDmaPatching</b> is set to 1, the <b>PreemptionAware</b> and <b>MultiEngineAware</b> members  must also be set to a value of 1. If <b>NoDmaPatching</b> is set to 1 but <b>PreemptionAware</b> or <b>MultiEngineAware</b> are set to zero, the operating system will halt the driver initialization process and return a failure code.</div>
<div> </div>
Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x0000008).

Supported starting with Windows 8.


### -field CancelCommandAware

A UINT value that specifies whether the driver supports cleaning up internal resources (through the <a href="https://msdn.microsoft.com/c290c313-14ee-4554-9bb1-8adec1892426">DxgkDdiCancelCommand</a> function) after a command is removed from the hardware queue.

If <b>CancelCommandAware</b> is set to 1 (<b>TRUE</b>), the driver supports cleaning up resources associated with a canceled DMA packet. If <b>CancelCommandAware</b> is set to zero (<b>FALSE</b>), the driver does not support cleaning up resources.

<div class="alert"><b>Note</b>  If <b>CancelCommandAware</b> is set to 1, the <b>MultiEngineAware</b> member  must also be set to a value of 1. If <b>CancelCommandAware</b> is set to 1 but <b>MultiEngineAware</b> is set to zero, the operating system returns a failure code.</div>
<div> </div>
Setting this member is equivalent to setting the fifth bit of the 32-bit <b>Value</b> member (0x0000010).

Supported starting with Windows 8.


### -field No64BitAtomics

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>TRUE</dt>
</dl>
</td>
<td width="60%">
Indicates a GPU is capable of only updating 32 bit values atomically. In this case, the OS will handle the fence wraparound case automatically, however it will place a restriction that an outstanding wait and signal fence values cannot be more than <b>UINT_MAX</b>/2 apart from the last signaled fence value.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>FALSE</dt>
</dl>
</td>
<td width="60%">
Indicates a GPU is capable of updating 64 bit values atomically as visible by the CPU.

</td>
</tr>
</table>
 

Supported starting with Windows 10.


### -field LowIrqlPreemptCommand

 


### -field HwQueuePacketCap

 


### -field Reserved


        This member is reserved and should be set to zero.


        This member is reserved and should be set to zero.

Setting this member to zero is equivalent to setting the remaining 27 bits (0xFFFFFFE0) of the 32-bit <b>Value</b> member to zeros.

Supported starting with Windows 8.

This member is reserved and should be set to zero. 

Setting this member to zero is equivalent to setting the remaining 30 bits (0xFFFFFFC) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A member in the union that DXGK_VIDSCHCAPS contains that can hold a 32-bit value that identifies the GPU scheduling capabilities that the driver can support.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561062">DXGK_DRIVERCAPS</a>



<a href="https://msdn.microsoft.com/c290c313-14ee-4554-9bb1-8adec1892426">DxgkDdiCancelCommand</a>



<a href="https://msdn.microsoft.com/aea21a36-f3d5-4541-bd2d-aa026668c562">DxgkDdiCreateContext</a>



<a href="https://msdn.microsoft.com/c21f62ab-c52e-43a2-a3a1-6fd6e5fbde01">DxgkDdiDestroyContext</a>



<a href="https://msdn.microsoft.com/363be784-0e3b-4f9a-a643-80857478bbae">DxgkDdiPatch</a>



<a href="https://msdn.microsoft.com/1a46b129-1e78-44e6-a609-59eab206692b">DxgkDdiPresent</a>



<a href="https://msdn.microsoft.com/fd634768-5e1e-4f40-82fd-5ef69148c3d7">DxgkDdiRender</a>
 

 

