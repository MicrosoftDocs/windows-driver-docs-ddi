---
UID: NS:d3dkmthk._D3DKMT_CREATEDEVICEFLAGS
title: "_D3DKMT_CREATEDEVICEFLAGS"
author: windows-driver-content
description: The D3DKMT_CREATEDEVICEFLAGS structure identifies the type of device context to be created in a call to the D3DKMTCreateDevice function.
old-location: display\d3dkmt_createdeviceflags.htm
old-project: display
ms.assetid: 90d4ce0a-1f36-4f2e-bdbe-5f80c8dfb92a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_CREATEDEVICEFLAGS, D3DKMT_CREATEDEVICEFLAGS structure [Display Devices], OpenGL_Structs_7cb495c3-44aa-46cb-8bca-87b66c5d422f.xml, _D3DKMT_CREATEDEVICEFLAGS, d3dkmthk/D3DKMT_CREATEDEVICEFLAGS, display.d3dkmt_createdeviceflags
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_CREATEDEVICEFLAGS
product: Windows
targetos: Windows
req.typenames: D3DKMT_CREATEDEVICEFLAGS
---

# _D3DKMT_CREATEDEVICEFLAGS structure


## -description


The D3DKMT_CREATEDEVICEFLAGS structure identifies the type of device context to be created in a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546836">D3DKMTCreateDevice</a> function.


## -struct-fields




### -field LegacyMode

A UINT value that specifies whether the device should imitate several behaviors of legacy devices (that is, from Microsoft DirectDraw through Microsoft Direct3D 9.0 device types).

When legacy mode is enabled, the video memory manager does not allow the device to allocate more video memory than can fit in the combined GPU segment. Primaries are allocated in place in video memory and not preserved across mode switches. 

Setting this member is equivalent to setting the first bit of a 32-bit value (0x00000001).


### -field RequestVSync

A UINT value that specifies whether the device requires vertical sync to operate. If <b>RequestVSync</b> is set, the operating system will enable vertical sync on the graphics hardware until the display device is released. 

Setting this member is equivalent to setting the second bit of a 32-bit value (0x00000002).


### -field DisableGpuTimeout

Supported in Windows 8 and later versions.A UINT value that specifies whether the device has disabled <a href="https://msdn.microsoft.com/f410eec7-026f-41e0-8c60-72f651659ead">Timeout Detection and Recovery (TDR)</a>.

Setting this member is equivalent to setting the second bit of a 32-bit value (0x00000004).


### -field Reserved

This member is reserved and should be set to zero. Setting this member is equivalent to setting the remaining 29 bits (0xFFFFFFF8) of a 32-bit value to zeros.

This member is reserved and should be set to zero. Setting this member is equivalent to setting the remaining 30 bits (0xFFFFFFFC) of a 32-bit value to zeros.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547819">D3DKMT_CREATEDEVICE</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_CREATEDEVICEFLAGS structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

