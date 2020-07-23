---
UID: NS:d3dkmddi._DXGKARG_COMMITVIDPN_FLAGS
title: _DXGKARG_COMMITVIDPN_FLAGS (d3dkmddi.h)
description: The DXGKARG_COMMITVIDPN_FLAGS structure identifies details about a call to the DxgkDdiCommitVidPn function.
old-location: display\dxgkarg_commitvidpn_flags.htm
ms.assetid: 02fe4216-101e-4ba7-88df-029f8bba9c17
ms.date: 05/10/2018
keywords: ["_DXGKARG_COMMITVIDPN_FLAGS structure"]
ms.keywords: DXGKARG_COMMITVIDPN_FLAGS, DXGKARG_COMMITVIDPN_FLAGS structure [Display Devices], DmStructs_267e916a-7058-4ce7-892d-9ed9d6f74bce.xml, _DXGKARG_COMMITVIDPN_FLAGS, d3dkmddi/DXGKARG_COMMITVIDPN_FLAGS, display.dxgkarg_commitvidpn_flags
f1_keywords:
 - "d3dkmddi/DXGKARG_COMMITVIDPN_FLAGS"
 - "DXGKARG_COMMITVIDPN_FLAGS"
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
- DXGKARG_COMMITVIDPN_FLAGS
targetos: Windows
tech.root: display
req.typenames: DXGKARG_COMMITVIDPN_FLAGS
---

# _DXGKARG_COMMITVIDPN_FLAGS structure


## -description


The DXGKARG_COMMITVIDPN_FLAGS structure identifies details about a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_commitvidpn">DxgkDdiCommitVidPn</a> function.


## -struct-fields




### -field PathPowerTransition

A UINT value that specifies whether the Microsoft DirectX graphics kernel subsystem calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_commitvidpn">DxgkDdiCommitVidPn</a> function to power off a connected monitor.

If <b>PathPowerTransition</b> is set to <b>TRUE</b>, the display miniport driver can optimize this call for a power down (for example, the driver might disable vertical syncs). The driver must also be aware that it might still receive calls to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_present">DxgkDdiPresent</a> function on the affected source.

Setting this member is equivalent to setting the first bit of a 32-bit value (0x00000001).

For more information, see the following Remarks section.


### -field PathPoweredOff

A UINT value that specifies whether the DirectX graphics kernel subsystem calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_commitvidpn">DxgkDdiCommitVidPn</a> to inform the driver that the user changed modes.

If <b>PathPoweredOff</b> is set to <b>TRUE</b>, the display miniport driver should expect present operations that are based on the new topology. The driver cannot perform any operations that would cause the topology path to be powered on again (for example, the driver cannot enable vertical syncs) because the monitor should now be powered off.

If <b>PathPoweredOff</b> is set to <b>FALSE</b>, the topology path is powered on. The display miniport driver should program hardware for present operations that are based on the former topology path, and the driver should commit hardware to support this topology path. Setting this member is equivalent to setting the second bit of a 32-bit value (0x00000002).

For more information, see the following Remarks section.


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 30 bits (0xFFFFFFFC) of a 32-bit value to zeros.


## -remarks



The DXGKARG_COMMITVIDPN_FLAGS structure stores information that the display miniport driver can use to determine how to respond to requested mode changes. With this information, the driver can distinguish between mode changes that occur during regular activity because an application requested a mode change, changes that occur because of power transitions, and changes that occur while monitors are turned off.

During regular activity, when the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_commitvidpn">DxgkDdiCommitVidPn</a> function is called, both <b>PathPowerTransition</b> and <b>PathPoweredOff</b> members will be <b>FALSE</b> so that the driver should apply mode changes immediately. Such mode changes are usually performed as isolated events. Therefore, there is no need for the driver to track any state that is associated with the previous mode configuration.

If monitors are being turned off or turned on, <b>PathPowerTransition</b> will be <b>TRUE</b> to indicate a power transition. In this case, a common pattern is that the monitors will be turned off, and then at some later time, the original configuration will be restored. It can be a significant workload for the driver to reset the display configuration completely after a system shutdown. Additionally, , the driver must continue to complete <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_present">DxgkDdiPresent</a> operations while the monitors are turned off. However, the driver can reduce its workload when a call is made to <i>DxgkDdiCommitVidPn</i> by making sure that the involved monitors are powered off. When power is restored, the driver workload to restore the display configuration will thereby be reduced.

Because the monitor might not be physically connected (at system resume time, for example), the driver should not rely on Windows to make a later call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_set_power_state">DxgkDdiSetPowerState</a> function to set the power state of the child device of the display adapter. However, Windows will still request that the CRTC is to be turned on. If the driver does not turn on vertical sync when it is requested to do so by the display mode manager (DMM), and if the user later reconnects the monitor, the monitor display might be blank.

<i>DxgkDdiPresent</i> operations must still be honored by the driver while monitors are turned off. The driver might have to act upon a mode change triggered by an application, for example to perform modifications to the rendering pipeline to account for rotation changes. Settings of <b>PathPowerTransition</b> = <b>FALSE</b> and <b>PathPoweredOff</b> = <b>TRUE</b> inform the driver that such a mode change has occurred. In this case, the driver must not turn on the monitors, but instead it should reprogram the hardware, if it is necessary, to accommodate the mode change so that additional <i>DxgkDdiPresent</i> operations can be completed. When such a mode change has been performed, and monitors are later turned back on, it is unlikely that the mode that occurred before the power down will be restored.

If a system resume operation is triggered after monitors were turned off for a system suspend operation, the driver can receive a <i>DxgkDdiCommitVidPn</i> call with both <b>PathPowerTransition</b> = <b>FALSE</b> and <b>PathPoweredOff</b> = <b>FALSE</b> before a <i>DxgkDdiCommitVidPn</i> call is made with <b>PathPowerTransition</b> = <b>TRUE</b>. This situation should only occur with an empty topology and, in this case, the driver should not turn monitors back on because the power transition is not yet completed.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_commitvidpn">DXGKARG_COMMITVIDPN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_present">DxgkDdiPresent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_set_power_state">DxgkDdiSetPowerState</a>
 

 

