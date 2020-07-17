---
UID: NS:d3dumddi._D3DDDIARG_GETCAPTUREALLOCATIONHANDLE
title: _D3DDDIARG_GETCAPTUREALLOCATIONHANDLE (d3dumddi.h)
description: The D3DDDIARG_GETCAPTUREALLOCATIONHANDLE structure describes the parameters for retrieving an allocation handle from a capture resource handle.
old-location: display\d3dddiarg_getcaptureallocationhandle.htm
tech.root: display
ms.assetid: 588ebf7a-db83-4eb8-8403-04b215bed12b
ms.date: 05/10/2018
keywords: ["_D3DDDIARG_GETCAPTUREALLOCATIONHANDLE structure"]
ms.keywords: D3DDDIARG_GETCAPTUREALLOCATIONHANDLE, D3DDDIARG_GETCAPTUREALLOCATIONHANDLE structure [Display Devices], UMDisplayDriver_param_Structs_8fece49c-e3e6-4683-b4af-517da6f73cc7.xml, _D3DDDIARG_GETCAPTUREALLOCATIONHANDLE, d3dumddi/D3DDDIARG_GETCAPTUREALLOCATIONHANDLE, display.d3dddiarg_getcaptureallocationhandle
f1_keywords:
 - "d3dumddi/D3DDDIARG_GETCAPTUREALLOCATIONHANDLE"
 - "D3DDDIARG_GETCAPTUREALLOCATIONHANDLE"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
- d3dumddi.h
api_name:
- D3DDDIARG_GETCAPTUREALLOCATIONHANDLE
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_GETCAPTUREALLOCATIONHANDLE
---

# _D3DDDIARG_GETCAPTUREALLOCATIONHANDLE structure


## -description


The D3DDDIARG_GETCAPTUREALLOCATIONHANDLE structure describes the parameters for retrieving an allocation handle from a capture resource handle. 


## -struct-fields




### -field hResource

[in] A handle to the capture resource that <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaptureallocationhandle">GetCaptureAllocationHandle</a> retrieves the allocation handle for.


### -field hAllocation

[out] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the allocation that is associated with the resource that <b>hResource</b> specifies.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaptureallocationhandle">GetCaptureAllocationHandle</a>
 

 

