---
UID: NS:d3dhal._D3DHAL_DRAWPRIMITIVES2DATA
title: "_D3DHAL_DRAWPRIMITIVES2DATA"
author: windows-driver-content
description: The D3DHAL_DRAWPRIMITIVES2DATA structure contains the information required by the D3dDrawPrimitives2 function to render primitives.
old-location: display\d3dhal_drawprimitives2data.htm
old-project: display
ms.assetid: d971e866-3049-4722-bfec-ca3364f291fd
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*LPD3DHAL_DRAWPRIMITIVES2DATA, D3DHAL_DRAWPRIMITIVES2DATA, D3DHAL_DRAWPRIMITIVES2DATA structure [Display Devices], LPD3DHAL_DRAWPRIMITIVES2DATA, LPD3DHAL_DRAWPRIMITIVES2DATA structure pointer [Display Devices], _D3DHAL_DRAWPRIMITIVES2DATA, d3dhal/D3DHAL_DRAWPRIMITIVES2DATA, d3dhal/LPD3DHAL_DRAWPRIMITIVES2DATA, d3dstrct_c9c3dea2-965c-4e98-8ff7-2928afe049fb.xml, display.d3dhal_drawprimitives2data"
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
-	d3dhal.h
api_name:
-	D3DHAL_DRAWPRIMITIVES2DATA
product: Windows
targetos: Windows
req.typenames: D3DHAL_DRAWPRIMITIVES2DATA
---

# _D3DHAL_DRAWPRIMITIVES2DATA structure


## -description


The D3DHAL_DRAWPRIMITIVES2DATA structure contains the information required by the <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a> function to render primitives.


## -struct-fields




### -field dwhContext

Specifies the context handle of the Direct3D device.


### -field dwFlags

Specifies flags that provide additional instructions to the driver or provide information from the driver. This member can be a bitwise OR of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3DHALDP2_EXECUTEBUFFER

</td>
<td>
The command and vertex buffers were created in system memory. The driver should update the state array that <b>lpdwRStates</b> points to. This flag is set by Direct3D only.

</td>
</tr>
<tr>
<td>
D3DHALDP2_REQCOMMANDBUFSIZE

</td>
<td>
The driver must be able to increase the current command buffer by at least the size specified in <b>dwReqCommandBufSize</b>. Drivers that do not support multibuffering of command buffers can ignore this flag. This flag is set by Direct3D only.

</td>
</tr>
<tr>
<td>
D3DHALDP2_REQVERTEXBUFSIZE

</td>
<td>
The driver must be able to allocate a vertex buffer of at least the size specified in <b>dwReqCommandBufSize</b>. Drivers that do not support multibuffering of vertex buffers can ignore this flag. This flag is set by Direct3D only.

</td>
</tr>
<tr>
<td>
D3DHALDP2_SWAPCOMMANDBUFFER

</td>
<td>
The driver can swap the buffer that <b>lpDDCommands</b> points to with a new command buffer and return immediately, asynchronously processing the original buffer while Direct3D fills the new command buffer. Drivers that do not support multibuffering of command buffers can ignore this flag. This flag is set by Direct3D only.

</td>
</tr>
<tr>
<td>
D3DHALDP2_SWAPVERTEXBUFFER

</td>
<td>
The driver can swap the buffer that <b>lpDDVertex</b> or <b>lpVertices</b> points to with a new vertex buffer and return immediately, asynchronously processing the original buffer while Direct3D fills the new vertex buffer. Drivers that do not support multibuffering of vertex buffers can ignore this flag. This flag is set by Direct3D only.

</td>
</tr>
<tr>
<td>
D3DHALDP2_USERMEMVERTICES

</td>
<td>
The <b>lpVertices</b> member is valid so the driver should obtain the vertex data from the user-allocated memory that <b>lpVertices</b> points to. This flag is set by Direct3D only.

</td>
</tr>
<tr>
<td>
D3DHALDP2_VIDMEMCOMMANDBUF

</td>
<td>
The command buffer allocated by the driver as a swap buffer is not in system memory. This flag can be set by drivers that support multibuffering of command buffers.

</td>
</tr>
<tr>
<td>
D3DHALDP2_VIDMEMVERTEXBUF

</td>
<td>
The vertex buffer allocated by the driver as a swap buffer is not in system memory. This flag can be set by drivers that support multibuffering of vertex buffers.

</td>
</tr>
</table>
 


### -field dwVertexType

Identifies the <a href="https://msdn.microsoft.com/206f4275-bcb8-4e8e-9c11-c6fb5d9c561d">FVF</a> of the data in the vertex buffer; that is, <b>dwVertexType</b> specifies which per-vertex data fields are present in the vertex buffer that <b>lpDDVertex</b> or <b>lpVertices</b> points to. This member can be a bitwise OR of the values in the following table. Only one of the <i>D3DFVF_TEXx</i> flags is set.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3DFVF_DIFFUSE

</td>
<td>
Each vertex has a diffuse color.

</td>
</tr>
<tr>
<td>
D3DFVF_SPECULAR

</td>
<td>
Each vertex has a specular color.

</td>
</tr>
<tr>
<td>
D3DFVF_TEX0

</td>
<td>
No texture coordinates are provided with the vertex data.

</td>
</tr>
<tr>
<td>
D3DFVF_TEX1

</td>
<td>
Each vertex has one set of texture coordinates.

</td>
</tr>
<tr>
<td>
D3DFVF_TEX2

</td>
<td>
Each vertex has two sets of texture coordinates.

</td>
</tr>
<tr>
<td>
D3DFVF_TEX3

</td>
<td>
Each vertex has three sets of texture coordinates.

</td>
</tr>
<tr>
<td>
D3DFVF_TEX4

</td>
<td>
Each vertex has four sets of texture coordinates.

</td>
</tr>
<tr>
<td>
D3DFVF_TEX5

</td>
<td>
Each vertex has five sets of texture coordinates.

</td>
</tr>
<tr>
<td>
D3DFVF_TEX6

</td>
<td>
Each vertex has six sets of texture coordinates.

</td>
</tr>
<tr>
<td>
D3DFVF_TEX7

</td>
<td>
Each vertex has seven sets of texture coordinates.

</td>
</tr>
<tr>
<td>
D3DFVF_TEX8

</td>
<td>
Each vertex has eight sets of texture coordinates.

</td>
</tr>
<tr>
<td>
D3DFVF_XYZRHW

</td>
<td>
Each vertex has <i>x, y, z,</i> and <i>w</i> coordinates. This flag is always set.

</td>
</tr>
</table>
 


### -field lpDDCommands



###### 



####### 



###### 



####### 


### -field dwCommandOffset



###### 



##### 



###### 



###### 


### -field dwCommandLength

Specifies the number of bytes of valid command data in the surface that <b>lpDDCommands</b> points to starting at <b>dwCommandOffset</b>.


### -field dwVertexOffset

Specifies the number of bytes into the surface pointed to by <b>lpDDVertex</b> or <b>lpVertices</b> where the vertex data starts.


### -field dwVertexLength

Specifies the number of vertices for which valid data exists in the surface pointed to by <b>lpDDVertex</b> or <b>lpVertices</b>. This valid data starts at <b>dwVertexOffset</b>.


### -field dwReqVertexBufSize

Specifies the minimum number of bytes that the driver must allocate for the swap vertex buffer. This member is valid only when the D3DHALDP2_REQVERTEXBUFSIZE flag is set. Drivers that do not support multibuffering of vertex buffers should ignore this member.


### -field dwReqCommandBufSize

Specifies the minimum number of bytes that the driver must increase the swap command buffer by. This member is valid only when the D3DHALDP2_REQCOMMANDBUFSIZE flag is set. Drivers that do not support multibuffering of command buffers should ignore this member.


### -field lpdwRStates

Points to a render state array that the driver should update when it parses render state commands from the command buffer. The driver should update this array only when the D3DHALDP2_EXECUTEBUFFER flag is set in <b>dwFlags</b>. The driver should use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549036">D3DRENDERSTATETYPE</a> enumerated types to update the appropriate element of the render state array. 


### -field dwErrorOffset



###### 



###### 



###### 



########  Each D3DHAL_DP2RESPONSEQUERY is followed by the following data related to the query:



#### BOOL for D3DQUERYTYPE_EVENT



#### DWORD for D3DQUERYTYPE_OCCLUSION



#### D3DDEVINFO_VCACHE structure for D3DQUERYTYPE_VCACHE



##### 



##### 


#### - ddrval

Specifies the location where the driver writes the return value of <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>. D3D_OK indicates success. Otherwise, the driver should return the appropriate D3DERR_<i>Xxx</i> error code. For more information, see <a href="https://msdn.microsoft.com/033beb6e-5872-4cb3-8f39-459e2fff82cd">Return Codes for Direct3D Driver Callbacks</a>.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3D_OK

</td>
<td>
The operation completed successfully.

</td>
</tr>
<tr>
<td>
D3DERR_COMMAND_UNPARSED

</td>
<td>
The driver requires the Direct3D runtime to parse the execute buffer.

</td>
</tr>
</table>
 


#### - dwVertexSize

Specifies the size of each vertex, in bytes. This member forms a union with <b>ddrval</b>.


#### - lpDDVertex

Points to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551733">DD_SURFACE_LOCAL</a> structure that identifies the DirectDraw surface containing the vertex data when the D3DHALDP2_USERMEMVERTICES flag is not set in <b>dwFlags</b>. Forms a union with <b>lpVertices</b>. 


#### - lpVertices

Points to a user-mode memory block containing vertex data when the D3DHALDP2_USERMEMVERTICES flag is set in <b>dwFlags</b>.


## -remarks



Note that the <b>dwVertexOffset</b> member specifies values in bytes; the <b>dwVertexLength</b> member specifies values in vertices. 

To calculate the valid data, in bytes, that exists in the surface at <b>lpDDVertex</b> or <b>lpVertices</b>, multiply the value in <b>dwVertexLength</b> by the value in <b>dwVertexSize</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549036">D3DRENDERSTATETYPE</a>



<a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551726">DD_SURFACE_GLOBAL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551733">DD_SURFACE_LOCAL</a>
 

 

