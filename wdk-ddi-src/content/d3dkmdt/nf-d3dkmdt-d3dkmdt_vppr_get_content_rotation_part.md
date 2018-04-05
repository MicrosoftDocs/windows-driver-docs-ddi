---
UID: NF:d3dkmdt.D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART
title: D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART function
author: windows-driver-content
description: A helper function that extracts the rotation angle from a given value of the D3DKMDT_VIDPN_PRESENT_PATH_ROTATION enumeration.
old-location: display\d3dkmdt_vppr_get_content_rotation_part.htm
old-project: display
ms.assetid: B533B0DD-B72C-4294-8E88-4C15EA1BB16E
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART, D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART function [Display Devices], d3dkmdt/D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART, display.d3dkmdt_vppr_get_content_rotation_part
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3_PATH_INDEPENDENT_ROTATION
req.target-min-winversvr: Windows Server 2012 R2
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
-	D3dkmdt.h
api_name:
-	D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART
product:
- Windows
targetos: Windows
req.typenames: DXGK_RENDER_PIPELINE_STAGE
---

# D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART function


## -description


A helper function that extracts the rotation angle from a given value of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546700">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION</a> enumeration. Only drivers that support path-independent rotation (DXGKDDI_INTERFACE_VERSION &gt;= DXGKDDI_INTERFACE_VERSION_WDDM1_3_PATH_INDEPENDENT_ROTATION) should call this function.


## -parameters




### -param Rotation

On input, a value from  the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546700">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION</a> enumeration.

On output, a value between 1 and 4, inclusive, that corresponds to the <b>ROTATION</b> portion of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546700">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION</a> constant values. An output value of 1 (identity) represents 0 degrees of rotation, 2 represents 90 degrees, and so on. An output value of 0 indicates that the VidPN path is not initialized.


## -returns



The returned value corresponds to the rotation angle as follows:<table>
<tr>
<td>Input enumeration value</td>
<td>Input enumeration constant</td>
<td>Rotation in degrees</td>
<td> Output <i>Rotation</i> value</td>
</tr>
<tr>
<td>0</td>
<td><b>D3DKMDT_VPPR_UNINITIALIZED</b></td>
<td>-</td>
<td>0</td>
</tr>
<tr>
<td>1</td>
<td><b>D3DKMDT_VPPR_IDENTITY</b></td>
<td>0</td>
<td>1</td>
</tr>
<tr>
<td>2</td>
<td><b>D3DKMDT_VPPR_ROTATE90</b></td>
<td>90</td>
<td>2</td>
</tr>
<tr>
<td>3</td>
<td><b>D3DKMDT_VPPR_ROTATE180</b></td>
<td>180</td>
<td>3</td>
</tr>
<tr>
<td>4</td>
<td><b>D3DKMDT_VPPR_ROTATE270</b></td>
<td>270</td>
<td>4</td>
</tr>
<tr>
<td>5</td>
<td><b>D3DKMDT_VPPR_IDENTITY_OFFSET90</b></td>
<td>0</td>
<td>1</td>
</tr>
<tr>
<td>6</td>
<td><b>D3DKMDT_VPPR_ROTATE90_OFFSET90</b></td>
<td>90</td>
<td>2</td>
</tr>
<tr>
<td>7</td>
<td><b>D3DKMDT_VPPR_ROTATE180_OFFSET90</b></td>
<td>180</td>
<td>3</td>
</tr>
<tr>
<td>8</td>
<td><b>D3DKMDT_VPPR_ROTATE270_OFFSET90</b></td>
<td>270</td>
<td>4</td>
</tr>
<tr>
<td>9</td>
<td><b>D3DKMDT_VPPR_IDENTITY_OFFSET180</b></td>
<td>0</td>
<td>1</td>
</tr>
<tr>
<td>10</td>
<td><b>D3DKMDT_VPPR_ROTATE90_OFFSET180</b></td>
<td>90</td>
<td>2</td>
</tr>
<tr>
<td>11</td>
<td><b>D3DKMDT_VPPR_ROTATE180_OFFSET180</b></td>
<td>180</td>
<td>3</td>
</tr>
<tr>
<td>12</td>
<td><b>D3DKMDT_VPPR_ROTATE270_OFFSET180</b></td>
<td>270</td>
<td>4</td>
</tr>
<tr>
<td>13</td>
<td><b>D3DKMDT_VPPR_IDENTITY_OFFSET270</b></td>
<td>0</td>
<td>1</td>
</tr>
<tr>
<td>14</td>
<td><b>D3DKMDT_VPPR_ROTATE90_OFFSET270</b></td>
<td>90</td>
<td>2</td>
</tr>
<tr>
<td>15</td>
<td><b>D3DKMDT_VPPR_ROTATE180_OFFSET270</b></td>
<td>180</td>
<td>3</td>
</tr>
<tr>
<td>16</td>
<td><b>D3DKMDT_VPPR_ROTATE270_OFFSET270</b></td>
<td>270</td>
<td>4</td>
</tr>
</table>
 






## -remarks



This function is declared inline in D3dkmdt.h as:

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>__inline
D3DKMDT_VIDPN_PRESENT_PATH_ROTATION 
    D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART(
        D3DKMDT_VIDPN_PRESENT_PATH_ROTATION Rotation)
{
    if ((Rotation &gt;= D3DKMDT_VPPR_IDENTITY_OFFSET90) &amp;&amp;
        (Rotation &lt;= D3DKMDT_VPPR_ROTATE270_OFFSET270))
    {
        Rotation = 
            (D3DKMDT_VIDPN_PRESENT_PATH_ROTATION)(
                ((Rotation - 1) % 4) + 1);
    }
    return Rotation;
}</pre>
</td>
</tr>
</table></span></div>
Your driver typically won't need to call this function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546700">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION</a>
 

 

