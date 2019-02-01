---
UID: NS:d3d10umddi.D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW
title: D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW (d3d10umddi.h)
description: The D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW structure describes a buffer that is used to create an unordered access view (UAV) in a call to the CreateUnorderedAccessView function.
old-location: display\d3d11ddiarg_buffer_unorderedaccessview.htm
ms.assetid: a5ff1158-539f-4b25-8b65-72d077108c46
ms.date: 05/10/2018
ms.keywords: D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW, D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW structure [Display Devices], UMDisplayDriver_Dx11param_Structs_c097052f-b667-43a9-8133-172770d9ab70.xml, d3d10umddi/D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW, display.d3d11ddiarg_buffer_unorderedaccessview
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d10umddi.h
api_name:
-	D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW
---

# D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW structure


## -description


The D3D11DDIARG_BUFFER_UNORDEREDACCESSVIEW structure describes a buffer that is used to create an unordered access view (UAV) in a call to the <a href="https://msdn.microsoft.com/c5a258e7-6645-46bb-ab2c-a1c8f5e593b7">CreateUnorderedAccessView</a> function. 


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




<a href="https://msdn.microsoft.com/6aca5d33-c8c6-4c6b-a66a-e28a958cbc2e">CalcPrivateUnorderedAccessViewSize</a>



<a href="https://msdn.microsoft.com/c5a258e7-6645-46bb-ab2c-a1c8f5e593b7">CreateUnorderedAccessView</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542086">D3D11DDIARG_CREATEUNORDEREDACCESSVIEW</a>
 

 

