---
UID: NS:d3dkmddi._DXGK_SEGMENTBANKPREFERENCE
title: _DXGK_SEGMENTBANKPREFERENCE (d3dkmddi.h)
description: The DXGK_SEGMENTBANKPREFERENCE structure describes bank preferences for paging in an allocation.
old-location: display\dxgk_segmentbankpreference.htm
ms.assetid: ff292137-4d95-4388-aae9-f6436b403c6a
ms.date: 05/10/2018
keywords: ["_DXGK_SEGMENTBANKPREFERENCE structure"]
ms.keywords: DXGK_SEGMENTBANKPREFERENCE, DXGK_SEGMENTBANKPREFERENCE structure [Display Devices], DmStructs_58615e96-0b7c-49a9-8966-0f627d7078f7.xml, _DXGK_SEGMENTBANKPREFERENCE, d3dkmddi/DXGK_SEGMENTBANKPREFERENCE, display.dxgk_segmentbankpreference
f1_keywords:
 - "d3dkmddi/DXGK_SEGMENTBANKPREFERENCE"
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
- DXGK_SEGMENTBANKPREFERENCE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_SEGMENTBANKPREFERENCE
---

# _DXGK_SEGMENTBANKPREFERENCE structure


## -description


The <b>DXGK_SEGMENTBANKPREFERENCE</b> structure describes bank preferences for paging in an allocation.


## -struct-fields




### -field Bank0

[out] The identifier of the highest priority preferred bank, or 0 if no preference is required. Valid values are from 1 to 127.

This member is equivalent to the first 7 bits of the 32-bit <b>Value</b> member (0x0000007F). 


### -field Direction0

[out] The direction in which <b>Bank0</b> should be scanned to locate a free area of memory. A value of 0 indicates a bottom-up search (that is, low address to high address), and a value of 1 indicates a top-bottom search (that is, high address to low address).

This member is equivalent to the eighth bit of the 32-bit <b>Value</b> member (0x00000080). 


### -field Bank1

[out] The identifier of the next highest priority preferred bank, or 0 if no preference is required. Valid values are from 1 to 127.

This member is equivalent to bits 9 through 15 of the 32-bit <b>Value</b> member (0x00007F00). 


### -field Direction1

[out] The direction in which <b>Bank1</b> should be scanned to locate a free hole of memory. A value of 0 indicates a bottom-up search (that is, low address to high address), and a value of 1 indicates a top-bottom search (that is, high address to low address).

This member is equivalent to the sixteenth bit of the 32-bit <b>Value</b> member (0x00008000). 


### -field Bank2

[out] The identifier of the next highest priority preferred bank, or 0 if no preference is required. Valid values are from 1 to 127.

This member is equivalent to bits 17 through 23 of the 32-bit <b>Value</b> member (0x007F0000). 


### -field Direction2

[out] The direction in which <b>Bank2</b> should be scanned to locate a free hole of memory. A value of 0 indicates a bottom-up search (that is, low address to high address), and a value of 1 indicates a top-bottom search (that is, high address to low address).

This member is equivalent to the twenty-fourth bit of the 32-bit <b>Value</b> member (0x00800000). 


### -field Bank3

[out] The identifier of the next highest priority preferred bank, or 0 if no preference is required. Valid values are from 1 to 127.

This member is equivalent to bits 25 through 31 of the 32-bit <b>Value</b> member (0x7F000000). 


### -field Direction3

[out] The direction in which <b>Bank3</b> should be scanned to locate a free hole of memory. A value of 0 indicates a bottom-up search (that is, low address to high address), and a value of 1 indicates a top-bottom search (that is, high address to low address).

This member is equivalent to the thirty-secondbit of the 32-bit <b>Value</b> member (0x80000000). 


### -field Value

[out] A member in the union that DXGK_SEGMENTBANKPREFERENCE contains that can hold a 32-bit value that identifies bank preferences.


## -remarks



The display miniport driver can indicate up to four bank preferences in the <b>HintedBank</b> member of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationinfo">DXGK_ALLOCATIONINFO</a> structure when the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation">DxgkDdiCreateAllocation</a> function is called. Preferred-bank identifiers are one-based (that is, the first bank has an identifier of one). An identifier of zero indicates that the driver has no preference. The highest priority preference is specified in the <b>Bank0</b> member; the lowest priority preference is specified in the <b>Bank3</b> member. The driver can specify less than four preferences by setting the lower priority preferences of bank identifiers to zero. For example, the driver can specify two preferences by setting <b>Bank0</b> and <b>Bank1</b> to valid identifiers and <b>Bank2</b> and <b>Bank3</b> to zero. The driver can use each <b>Direction</b><i>X</i> member to specify the scanning direction for each bank preference independently. 

 The video memory manager  allocates resources from  preferred segments that the <b>PreferredSegment</b> member of DXGK_ALLOCATIONINFO specifies. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationinfo">DXGK_ALLOCATIONINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationlist">DXGK_ALLOCATIONLIST</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff562047(v=vs.85)">DXGK_SEGMENTPREFERENCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation">DxgkDdiCreateAllocation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_render">DxgkDdiRender</a>
 

 

