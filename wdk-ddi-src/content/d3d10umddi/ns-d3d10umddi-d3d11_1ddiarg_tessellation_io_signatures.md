---
UID: NS:d3d10umddi.D3D11_1DDIARG_TESSELLATION_IO_SIGNATURES
title: D3D11_1DDIARG_TESSELLATION_IO_SIGNATURES (d3d10umddi.h)
description: Describes a tessellation I/O signature.
old-location: display\d3d11_1ddiarg_tessellation_io_signatures.htm
ms.assetid: 90b9cbba-6a8f-444e-b0eb-cfbabdd57dcf
ms.date: 05/10/2018
keywords: ["D3D11_1DDIARG_TESSELLATION_IO_SIGNATURES structure"]
ms.keywords: D3D11_1DDIARG_TESSELLATION_IO_SIGNATURES, D3D11_1DDIARG_TESSELLATION_IO_SIGNATURES structure [Display Devices], d3d10umddi/D3D11_1DDIARG_TESSELLATION_IO_SIGNATURES, display.d3d11_1ddiarg_tessellation_io_signatures
f1_keywords:
 - "d3d10umddi/D3D11_1DDIARG_TESSELLATION_IO_SIGNATURES"
 - "D3D11_1DDIARG_TESSELLATION_IO_SIGNATURES"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- D3d10umddi.h
api_name:
- D3D11_1DDIARG_TESSELLATION_IO_SIGNATURES
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDIARG_TESSELLATION_IO_SIGNATURES
---

# D3D11_1DDIARG_TESSELLATION_IO_SIGNATURES structure


## -description


Describes a tessellation I/O signature.


## -struct-fields




### -field pInputSignatureDeprecated

 


### -field pInputSignature

[in] An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_signature_entry">D3D11_1DDIARG_SIGNATURE_ENTRY</a> structures for the input part of a signature.


### -field NumInputSignatureEntries

[in] The number of entries in the array that the <b>pInputSignature</b> member specifies.


### -field pOutputSignatureDeprecated

 


### -field pOutputSignature

[in] An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_signature_entry">D3D11_1DDIARG_SIGNATURE_ENTRY</a> structures for the output part of a signature.


### -field NumOutputSignatureEntries

[in] The number of entries in the array that the <b>pOutputSignature</b> member specifies.


### -field pPatchConstantSignatureDeprecated

 


### -field pPatchConstantSignature

[in] An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_signature_entry">D3D11_1DDIARG_SIGNATURE_ENTRY</a> structures for the signature patches.


### -field NumPatchConstantSignatureEntries

[in] The number of entries in the array that the <b>pPatchConstantSignature</b> member specifies.


## -remarks



A signature is basically the union of all registers that are input and output by any shader that shares the signature. Therefore, a signature might be a superset of what a given shader might actually input or output. 

Hardware should determine that the upstream stage in the pipeline might provide some or all of the data in the signature that is laid out as the <b>pInputSignature</b> and <b>NumInputSignatureEntries</b> members specify. Similarly, hardware should determine that the downstream stage in the pipeline might consume some or all of the data in the signature that is laid out as the <b>pOutputSignature</b> and <b>NumOutputSignatureEntries</b> members specify.

To comply with the requirement for the event input and output registers to be reordered during shader compilation, the full signature is passed to the driver. Such reordering might depend on the driver being able to determine all of the registers in the signature, as well as which registers have system names (for example, names that the <b>SystemValue</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_signature_entry">D3D11_1DDIARG_SIGNATURE_ENTRY</a> structure specifies). Such reordering might also depend on the driver being able to determine registers that are not present in the current shader.

The declarations within the shader code itself also show which registers are actually used by a particular shader. These registers are possibly a subset of the input and output parts of the signature. If some hardware is not required to reorder input and output registers at compile time, the driver for that hardware can completely ignore the full signature that the <b>D3D11_1DDIARG_TESSELLATION_IO_SIGNATURES</b> structure provides. The reference rasterizer, for example, does not require the information that the <b>D3D11_1DDIARG_TESSELLATION_IO_SIGNATURES</b> structure provides.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_signature_entry">D3D11_1DDIARG_SIGNATURE_ENTRY</a>
 

 

