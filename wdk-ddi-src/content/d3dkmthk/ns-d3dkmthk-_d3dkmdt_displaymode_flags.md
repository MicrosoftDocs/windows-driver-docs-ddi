---
UID: NS:d3dkmthk._D3DKMDT_DISPLAYMODE_FLAGS
title: "_D3DKMDT_DISPLAYMODE_FLAGS"
author: windows-driver-content
description: The D3DKMDT_DISPLAYMODE_FLAGS structure identifies attributes of a display mode.
old-location: display\d3dkmdt_displaymode_flags.htm
old-project: display
ms.assetid: 0b45cd69-5c9e-4772-a68f-d604806e7789
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, 3, A, D, D3DKMDT_DISPLAYMODE_FLAGS, D3DKMDT_DISPLAYMODE_FLAGS structure [Display Devices], E, F, G, I, K, L, M, O, OpenGL_Structs_64aa66c8-8323-4cee-b437-16b8f3c361c8.xml, P, S, T, Y, _, _D3DKMDT_DISPLAYMODE_FLAGS, d3dkmthk/D3DKMDT_DISPLAYMODE_FLAGS, display.d3dkmdt_displaymode_flags"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMDT_DISPLAYMODE_FLAGS
product: Windows
targetos: Windows
req.typenames: D3DKMDT_DISPLAYMODE_FLAGS
---

# _D3DKMDT_DISPLAYMODE_FLAGS structure


## -description


The D3DKMDT_DISPLAYMODE_FLAGS structure identifies attributes of a display mode.


## -syntax


````
typedef struct _D3DKMDT_DISPLAYMODE_FLAGS {
#if (DXGKDDI_INTERFACE_VERSION < DXGKDDI_INTERFACE_VERSION_WIN8)
  BOOLEAN                     ValidatedAgainstMonitorCaps  :1;
  BOOLEAN                     RoundedFakeMode  :1;
  D3DKMDT_MODE_PRUNING_REASON ModePruningReason  :4;
  UINT                        Reserved  :28;
#else 
  UINT                        ValidatedAgainstMonitorCaps  :1;
  UINT                        RoundedFakeMode  :1;
  UINT                          :0;
  D3DKMDT_MODE_PRUNING_REASON ModePruningReason  :4;
  UINT                        Stereo  :1;
  UINT                        AdvancedScanCapable  :1;
  UINT                        Reserved  :26;
#endif 
} D3DKMDT_DISPLAYMODE_FLAGS;
````


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

[in] A value of type <a href="..\d3dkmthk\ne-d3dkmthk-_d3dkmdt_mode_pruning_reason.md">D3DKMDT_MODE_PRUNING_REASON</a> that identifies the reason why the monitor either supports the display mode or does not support the display mode. The four bits are defined by one of the values in the <b>D3DKMDT_MODE_PRUNING_REASON</b> enumeration type and depend on the setting of the <b>ValidatedAgainstMonitorCaps</b> member. For more information about how the <b>ModePruningReason</b> value is set, see <b>D3DKMDT_MODE_PRUNING_REASON</b>.

Setting this member is equivalent to setting bits 4 through 7 of a 32-bit value (0x0000003C).

[in] A value of type <a href="..\d3dkmthk\ne-d3dkmthk-_d3dkmdt_mode_pruning_reason.md">D3DKMDT_MODE_PRUNING_REASON</a> that identifies the reason why the monitor either supports the display mode or does not support the display mode. The four bits are defined by one of the values in the <b>D3DKMDT_MODE_PRUNING_REASON</b> enumeration type and depend on the setting of the <b>ValidatedAgainstMonitorCaps</b> member. For more information about how the <b>ModePruningReason</b> value is set, see <b>D3DKMDT_MODE_PRUNING_REASON</b>.

This member is equivalent to bits 4 through 7 of a 32-bit value (0x0000003C). 

Supported starting with Windows 8.


### -field Stereo

[in] 

A UINT value that specifies whether stereo is supported by the monitor that the display mode will be displayed on.

Setting this member is equivalent to setting the eighth bit of a 32-bit value (0x00000080).

Supported starting with Windows 8.


### -field AdvancedScanCapable

[in] A UINT value that specifies whether the driver supports the advanced scan capability.

The driver reports support for this option in the current display mode by setting the <b>Type</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_source_mode.md">D3DKMDT_VIDPN_SOURCE_MODE</a> structure to <b>D3DKMDT_RMT_GRAPHICS_STEREO_ADVANCED_SCAN</b>.

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

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_displaymode.md">D3DKMT_DISPLAYMODE</a>



<a href="..\d3dkmthk\ne-d3dkmthk-_d3dkmdt_mode_pruning_reason.md">D3DKMDT_MODE_PRUNING_REASON</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_DISPLAYMODE_FLAGS structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

