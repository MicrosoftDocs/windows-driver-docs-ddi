---
UID: NS:d3dkmddi._DXGK_DEVICEINFOFLAGS
title: "_DXGK_DEVICEINFOFLAGS"
author: windows-driver-content
description: The DXGK_DEVICEINFOFLAGS structure identifies, in bit-field flags, information about a graphics device.
old-location: display\dxgk_deviceinfoflags.htm
old-project: display
ms.assetid: 26d0aad9-86d0-4d97-978a-1e15285d3369
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, A, C, D, DXGK_DEVICEINFOFLAGS, DXGK_DEVICEINFOFLAGS structure [Display Devices], DmStructs_69e769da-b68e-4df6-94dd-95e11bc88b0c.xml, E, F, G, I, K, L, N, O, S, V, X, _, _DXGK_DEVICEINFOFLAGS, d3dkmddi/DXGK_DEVICEINFOFLAGS, display.dxgk_deviceinfoflags"
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
-	DXGK_DEVICEINFOFLAGS
product: Windows
targetos: Windows
req.typenames: DXGK_DEVICEINFOFLAGS
---

# _DXGK_DEVICEINFOFLAGS structure


## -description


The DXGK_DEVICEINFOFLAGS structure identifies, in bit-field flags, information about a graphics device.


## -syntax


````
typedef struct _DXGK_DEVICEINFOFLAGS {
  union {
    struct {
      UINT GuaranteedDmaBufferContract  :1;
      UINT Reserved  :31;
    };
    UINT Value;
  };
} DXGK_DEVICEINFOFLAGS;
````


## -struct-fields




### -field GuaranteedDmaBufferContract

[out] Obsolete. A UINT value that specifies whether the device that is created through a call to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a> uses the guaranteed contract model for direct memory access (DMA) buffers. For more information about the guaranteed contract model, see <a href="https://msdn.microsoft.com/fee6f7eb-157b-466d-b482-110a48045283">Using the Guaranteed Contract DMA Buffer Model</a>. If this member is set, the device uses the guaranteed contract model; if this member is not set, the device does not use the guaranteed contract model. The display driver model for Windows Vista currently supports only the guaranteed contract DMA buffer model. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Reserved

[out] This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.


#### - Value

[out] A member in the union that DXGK_DEVICEINFOFLAGS contains that can hold a 32-bit value that indicates information about a graphics device.


## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_deviceinfo.md">DXGK_DEVICEINFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_DEVICEINFOFLAGS structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

