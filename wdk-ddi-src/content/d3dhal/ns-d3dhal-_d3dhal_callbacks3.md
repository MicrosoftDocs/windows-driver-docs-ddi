---
UID: NS:d3dhal._D3DHAL_CALLBACKS3
title: _D3DHAL_CALLBACKS3
author: windows-driver-content
description: D3DHAL_CALLBACKS3 is one of several callback structures that describe the Direct3D support provided by the driver.
old-location: display\d3dhal_callbacks3.htm
old-project: display
ms.assetid: 09215332-4ee3-4f7b-be25-091b8d85fd6b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DHAL_CALLBACKS3, D3DHAL_CALLBACKS3, *LPD3DHAL_CALLBACKS3, *LPD3DHAL_CALLBACKS3
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DHAL_CALLBACKS3
req.alt-loc: d3dhal.h
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
req.typenames: D3DHAL_CALLBACKS3, *LPD3DHAL_CALLBACKS3
---

# _D3DHAL_CALLBACKS3 structure



## -description
D3DHAL_CALLBACKS3 is one of several callback structures that describe the Direct3D support provided by the driver.



## -syntax

````
typedef struct _D3DHAL_CALLBACKS3 {
  DWORD                                dwSize;
  DWORD                                dwFlags;
  LPD3DHAL_CLEAR2CB                    Clear2;
  LPVOID                               lpvReserved;
  LPD3DHAL_VALIDATETEXTURESTAGESTATECB ValidateTextureStageState;
  LPD3DHAL_DRAWPRIMITIVES2CB           DrawPrimitives2;
} D3DHAL_CALLBACKS3, *LPD3DHAL_CALLBACKS3;
````


## -struct-fields

### -field dwSize

Specifies the size in bytes of this structure.


### -field dwFlags

Indicates the callbacks associated with this structure that the driver has implemented. For every bit the driver sets in <b>dwFlags</b>, the driver must initialize the corresponding function pointer member of this structure. This member can be the bitwise-OR of one or more of the following flags:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3DHAL3_CB32_CLEAR2

</td>
<td>
Not used in DirectX 7.0 and later versions.

</td>
</tr>
<tr>
<td>
D3DHAL3_CB32_DRAWPRIMITIVES2

</td>
<td>
The <b>DrawPrimitives2</b> member points to a driver-implemented <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> callback.

</td>
</tr>
<tr>
<td>
D3DHAL3_CB32_RESERVED

</td>
<td>
Not used in DirectX 7.0 and later versions.

</td>
</tr>
<tr>
<td>
D3DHAL3_CB32_VALIDATETEXTURESTAGESTATE

</td>
<td>
The <b>ValidateTextureStageState</b> member points to a driver-implemented <a href="https://msdn.microsoft.com/library/windows/hardware/ff549064">D3dValidateTextureStageState</a> callback.

</td>
</tr>
</table>
 


### -field Clear2

Must be set to <b>NULL</b>. This was a pointer to the driver-supplied <b>D3dClear2</b> callback that is no longer used for DirectX 7.0 and beyond. Instead the driver should respond to the D3DDP2OP_CLEAR command stream token in its implementation of <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>.


### -field lpvReserved

Specifies a reserved field and must be set to <b>NULL</b> in a Windows 2000 and later driver.


### -field ValidateTextureStageState

Points to the driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff549064">D3dValidateTextureStageState</a> callback, or <b>NULL</b>. Drivers that support multitexturing must implement the callback that this member points to.


### -field DrawPrimitives2

Points to the driver-supplied <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> callback. A driver must implement the callback that this member points to.


## -remarks
The driver allocates this structure and sets appropriate values in all members. The driver's <a href="https://msdn.microsoft.com/89a22163-a678-4c72-932a-ae4d17922e0b">DdGetDriverInfo</a> function returns a pointer to this structure when that function is called with the GUID_D3DCallbacks3 GUID.


## -see-also
<dl>
<dt>D3DDP2OP_CLEAR</dt>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_d3dhal_callbacks.md">D3DHAL_CALLBACKS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549064">D3dValidateTextureStageState</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/89a22163-a678-4c72-932a-ae4d17922e0b">DdGetDriverInfo</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_CALLBACKS3 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

