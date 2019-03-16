---
UID: NS:d3dkmthk._D3DKMDT_DISPLAYMODE_FLAGS
title: _D3DKMDT_DISPLAYMODE_FLAGS (d3dkmthk.h)
description: The D3DKMDT_DISPLAYMODE_FLAGS structure identifies attributes of a display mode.
old-location: display\d3dkmdt_displaymode_flags.htm
ms.assetid: 0b45cd69-5c9e-4772-a68f-d604806e7789
ms.date: 05/10/2018
ms.keywords: D3DKMDT_DISPLAYMODE_FLAGS, D3DKMDT_DISPLAYMODE_FLAGS structure [Display Devices], OpenGL_Structs_64aa66c8-8323-4cee-b437-16b8f3c361c8.xml, _D3DKMDT_DISPLAYMODE_FLAGS, d3dkmthk/D3DKMDT_DISPLAYMODE_FLAGS, display.d3dkmdt_displaymode_flags
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
- d3dkmthk.h
api_name:
- D3DKMDT_DISPLAYMODE_FLAGS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMDT_DISPLAYMODE_FLAGS
---

# _D3DKMDT_DISPLAYMODE_FLAGS structure


## -description


The D3DKMDT_DISPLAYMODE_FLAGS structure identifies attributes of a display mode.


## -struct-fields




### -field ValidatedAgainstMonitorCaps

A Boolean value that specifies whether the display mode is supported by the monitor that the display mode will be displayed on.

Setting this member is equivalent to setting the first bit of a 32-bit value (0x00000001).

A UINT value that specifies whether the display mode is supported by the monitor that the display mode will be displayed on.

Setting this member is equivalent to setting the first bit of a 32-bit value (0x00000001).

Supported starting with Windows 8.


### -field RoundedFakeMode

A Boolean value that specifies whether the display mode is rounded.

Setting this member is equivalent to setting the second bit of a 32-bit value (0x00000002).

A UINT value that specifies whether the display mode is rounded.

Setting this member is equivalent to setting the second bit of a 32-bit value (0x00000002).

Supported starting with Windows 8.


### -field ModePruningReason

[in] A value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff546070">D3DKMDT_MODE_PRUNING_REASON</a> that identifies the reason why the monitor either supports the display mode or does not support the display mode. The four bits are defined by one of the values in the <b>D3DKMDT_MODE_PRUNING_REASON</b> enumeration type and depend on the setting of the <b>ValidatedAgainstMonitorCaps</b> member. For more information about how the <b>ModePruningReason</b> value is set, see <b>D3DKMDT_MODE_PRUNING_REASON</b>.

Setting this member is equivalent to setting bits 4 through 7 of a 32-bit value (0x0000003C).

[in] A value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff546070">D3DKMDT_MODE_PRUNING_REASON</a> that identifies the reason why the monitor either supports the display mode or does not support the display mode. The four bits are defined by one of the values in the <b>D3DKMDT_MODE_PRUNING_REASON</b> enumeration type and depend on the setting of the <b>ValidatedAgainstMonitorCaps</b> member. For more information about how the <b>ModePruningReason</b> value is set, see <b>D3DKMDT_MODE_PRUNING_REASON</b>.

This member is equivalent to bits 4 through 7 of a 32-bit value (0x0000003C). 

Supported starting with Windows 8.


### -field Stereo

[in] 

A UINT value that specifies whether stereo is supported by the monitor that the display mode will be displayed on.

Setting this member is equivalent to setting the eighth bit of a 32-bit value (0x00000080).

Supported starting with Windows 8.


### -field AdvancedScanCapable

[in] A UINT value that specifies whether the driver supports the advanced scan capability.

The driver reports support for this option in the current display mode by setting the <b>Type</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546724">D3DKMDT_VIDPN_SOURCE_MODE</a> structure to <b>D3DKMDT_RMT_GRAPHICS_STEREO_ADVANCED_SCAN</b>.

Setting this member is equivalent to setting the ninth bit of a 32-bit value (0x00000100).

Supported starting with Windows 8.


### -field PreferredTiming

 


### -field PhysicalModeSupported

 


### -field Reserved

This member is reserved and should be set to zero. Setting this member is equivalent to setting the remaining 28 bits (0xFFFFFFF0) of a 32-bit value to zeros.

This member is reserved and should be set to zero.

Setting this member is equivalent to setting the remaining 26 bits (0xFFFFFFC0) of a 32-bit value to zeros.

Supported starting with Windows 8.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546070">D3DKMDT_MODE_PRUNING_REASON</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547942">D3DKMT_DISPLAYMODE</a>
 

 

