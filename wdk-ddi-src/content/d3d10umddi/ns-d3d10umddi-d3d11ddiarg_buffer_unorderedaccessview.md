---
UID: NS:d3d10umddi.D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW
title: D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW (d3d10umddi.h)
description: The D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW structure describes a buffer that is used to create an unordered access view (UAV) in a call to the CreateUnorderedAccessView function.
old-location: display\d3d11ddiarg_buffer_unorderedaccessview.htm
ms.date: 05/10/2018
keywords: ["D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW structure"]
ms.keywords: D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW, D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW structure [Display Devices], UMDisplayDriver_Dx11param_Structs_c097052f-b667-43a9-8133-172770d9ab70.xml, d3d10umddi/D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW, display.d3d11ddiarg_buffer_unorderedaccessview
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW is supported beginning with the Windows 7 operating system.
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
targetos: Windows
tech.root: display
req.typenames: D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW
f1_keywords:
 - D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW
 - d3d10umddi/D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW
---

# D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW structure


## -description

The D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW structure describes a buffer that is used to create an unordered access view (UAV) in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createunorderedaccessview">CreateUnorderedAccessView</a> function.

## -struct-fields

### -field FirstElement

[in] The offset, in bytes, to the first element in the buffer.

### -field NumElements

[in] The number of elements in the buffer.

### -field Flags

[in] A valid bitwise OR of flag values that describe the buffer. The Direct3D runtime supports the following values.

|Value|Meaning|
|--- |--- |
|D3D11_DDI_BUFFER_UAV_FLAG_RAW (0x00000001)|The buffer is in raw format.|
|D3D11_DDI_BUFFER_UAV_FLAG_APPEND (0x00000002)|Associate a counter with the UAV that has append semantics. The count reflects how many items are stored. However, the order in which the items are stored can change.|
|D3D11_DDI_BUFFER_UAV_FLAG_COUNTER (0x00000004)|Associate a counter with the UAV whose semantics prevent the reordering of the contents of the UAV. Therefore, applications can depend on the storage order. For example, applications can create linked lists by using count values to reference stored items.|

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_calcprivateunorderedaccessviewsize">CalcPrivateUnorderedAccessViewSize</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createunorderedaccessview">CreateUnorderedAccessView</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createunorderedaccessview">D3D11DDIARG_CREATEUNORDEREDACCESSVIEW</a>
