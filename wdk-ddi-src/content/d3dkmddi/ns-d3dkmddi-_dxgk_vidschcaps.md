---
UID: NS:d3dkmddi._DXGK_VIDSCHCAPS
title: _DXGK_VIDSCHCAPS
author: windows-driver-content
description: The DXGK_VIDSCHCAPS structure identifies the graphics processing unit (GPU) scheduling capabilities, in bit-field flags, that a driver can support.
old-location: display\dxgk_vidschcaps.htm
old-project: display
ms.assetid: 714741b5-aec1-4d79-8199-00e8d97e6637
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGK_VIDSCHCAPS, display.dxgk_vidschcaps, d3dkmddi/DXGK_VIDSCHCAPS, _DXGK_VIDSCHCAPS, DmStructs_01f721e4-8585-46b1-a911-9fa904a29f7e.xml, DXGK_VIDSCHCAPS structure [Display Devices]
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
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	d3dkmddi.h
apiname: 
-	DXGK_VIDSCHCAPS
product: Windows
targetos: Windows
req.typenames: DXGK_VIDSCHCAPS
---

# _DXGK_VIDSCHCAPS structure


## -description


The DXGK_VIDSCHCAPS structure identifies the graphics processing unit (GPU) scheduling capabilities, in bit-field flags, that a driver can support.


## -syntax


````
typedef struct _DXGK_VIDSCHCAPS {
  union {
    struct {
      UINT MultiEngineAware  :1;
      UINT VSyncPowerSaveAware  :1;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
      UINT PreemptionAware  :1;
      UINT NoDmaPatching  :1;
      UINT CancelCommandAware  :1;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_0)
      UINT No64BitAtomics  :1;
      UINT Reserved  :26;
#else 
      UINT Reserved  :27;
#endif 
#else 
      UINT Reserved  :30;
#endif 
    };
    UINT Value;
  };
} DXGK_VIDSCHCAPS;
````


## -struct-fields




### -field MultiEngineAware

A UINT value that specifies whether the driver supports the creation and destruction of a device context (through the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a> and <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_destroycontext.md">DxgkDdiDestroyContext</a> functions) and the use of a device context (through the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_present.md">DxgkDdiPresent</a> and <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_render.md">DxgkDdiRender</a> functions). If the driver does not support context creation, for every call to the driver that would pass a handle to a context, the Microsoft DirectX graphics kernel subsystem replaces the handle to the context with a handle to the device.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field VSyncPowerSaveAware

A UINT value that specifies whether the driver supports vertical-sync power-saving functionality. 
        

If <b>VSyncPowerSaveAware</b> is set to 1 (<b>TRUE</b>), the operating system can save power by disabling and enabling the vertical-sync interrupt that occurs from the usage of some applications. If <b>VSyncPowerSaveAware</b> is set to zero (<b>FALSE</b>), the operating system will never disable the vertical-sync interrupt for applications that might cause the vertical-sync interrupt to occur.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).

Supported starting with Windows Server 2008 and Windows Vista with SP1.


### -field PreemptionAware

A UINT value that specifies whether the driver supports the   GPU preemption policy of Windows 8 and later versions of Windows. With this policy, the operating system always issues preemption requests to the GPU before it initiates the <mshelp:link keywords="display.timeout_detection_and_recovery" tabindex="0">Timeout Detection and Recovery
(TDR)</mshelp:link> process.
        

If <b>PreemptionAware</b> is set to 1 (<b>TRUE</b>), the driver supports the preemption policy of Windows 8 and later versions of Windows.

If <b>PreemptionAware</b> is set to zero (<b>FALSE</b>), the driver supports the preemption policy  of Windows 7. With this policy, the operating system may not issue preemption requests while potentially long running operations are being executed on the GPU. As a result, these GPU requests are not preempted  before the TDR process is initiated. This may cause the TDR process to repeatedly reset the GPU which could lead to a system stop error.
<div class="alert"><b>Note</b>  If <b>PreemptionAware</b> is set to 1, the <b>MultiEngineAware</b> member  must also be set to a value of 1. If <b>PreemptionAware</b> is set to 1 but <b>MultiEngineAware</b> is set to zero, the operating system will halt the driver initialization process and return a failure code.</div><div> </div>Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).

Supported starting with Windows 8.


### -field NoDmaPatching

A UINT value that specifies whether the driver disables leak detection for DMA buffers that are split into multiple parts. This detection is performed after the driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_patch.md">DxgkDdiPatch</a> function is called to assign, or <i>patch</i>, physical addresses to each part of the DMA buffer.
<div class="alert"><b>Note</b>  Display devices that support virtual addresses can reprogram a virtual address to a new video memory location without having to patch the value of the DMA buffer address. For these types of display devices, the driver should set <b>NoDmaPatching</b> to 1.</div><div> </div>If <b>NoDmaPatching</b> is set to 1 (<b>TRUE</b>), the driver disables leak detection, and the behavior of DMA buffer splitting is the same as in Windows 7.

If <b>NoDmaPatching</b> is set to 0 (<b>FALSE</b>), the driver enables leak detection for patched DMA buffer addresses. The operating system performs leak detection before it calls the driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_patch.md">DxgkDdiPatch</a> function.
<div class="alert"><b>Note</b>  If <b>NoDmaPatching</b> is set to 1, the <b>PreemptionAware</b> and <b>MultiEngineAware</b> members  must also be set to a value of 1. If <b>NoDmaPatching</b> is set to 1 but <b>PreemptionAware</b> or <b>MultiEngineAware</b> are set to zero, the operating system will halt the driver initialization process and return a failure code.</div><div> </div>Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x0000008).

Supported starting with Windows 8.


### -field CancelCommandAware

A UINT value that specifies whether the driver supports cleaning up internal resources (through the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_cancelcommand.md">DxgkDdiCancelCommand</a> function) after a command is removed from the hardware queue.

If <b>CancelCommandAware</b> is set to 1 (<b>TRUE</b>), the driver supports cleaning up resources associated with a canceled DMA packet. If <b>CancelCommandAware</b> is set to zero (<b>FALSE</b>), the driver does not support cleaning up resources.
<div class="alert"><b>Note</b>  If <b>CancelCommandAware</b> is set to 1, the <b>MultiEngineAware</b> member  must also be set to a value of 1. If <b>CancelCommandAware</b> is set to 1 but <b>MultiEngineAware</b> is set to zero, the operating system returns a failure code.</div><div> </div>Setting this member is equivalent to setting the fifth bit of the 32-bit <b>Value</b> member (0x0000010).

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

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_cancelcommand.md">DxgkDdiCancelCommand</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_render.md">DxgkDdiRender</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_patch.md">DxgkDdiPatch</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_destroycontext.md">DxgkDdiDestroyContext</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_present.md">DxgkDdiPresent</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_VIDSCHCAPS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

