---
UID: NF:d3dkmdt.D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART
title: D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART function
author: windows-driver-content
description: A helper function that extracts the rotation angle from a given value of the D3DKMDT_VIDPN_PRESENT_PATH_ROTATION enumeration.
old-location: display\d3dkmdt_vppr_get_content_rotation_part.htm
old-project: display
ms.assetid: B533B0DD-B72C-4294-8E88-4C15EA1BB16E
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART, d3dkmdt/D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART, D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART function [Display Devices], display.d3dkmdt_vppr_get_content_rotation_part
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3dkmdt.h
apiname:
-	D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART
product: Windows
targetos: Windows
req.typenames: DXGK_RENDER_PIPELINE_STAGE
---

# D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART function


## -description


A helper function that extracts the rotation angle from a given value of the <a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_vidpn_present_path_rotation.md">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION</a> enumeration. Only drivers that support path-independent rotation (DXGKDDI_INTERFACE_VERSION &gt;= DXGKDDI_INTERFACE_VERSION_WDDM1_3_PATH_INDEPENDENT_ROTATION) should call this function.


## -syntax


````
__inline
D3DKMDT_VIDPN_PRESENT_PATH_ROTATION
           D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART(
   D3DKMDT_VIDPN_PRESENT_PATH_ROTATION Rotation
);
````


## -parameters




### -param Rotation

On input, a value from  the <a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_vidpn_present_path_rotation.md">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION</a> enumeration.

On output, a value between 1 and 4, inclusive, that corresponds to the <b>ROTATION</b> portion of the <a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_vidpn_present_path_rotation.md">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION</a> constant values. An output value of 1 (identity) represents 0 degrees of rotation, 2 represents 90 degrees, and so on. An output value of 0 indicates that the VidPN path is not initialized.


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
</table></span></div>Your driver typically won't need to call this function.



## -see-also

<a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_vidpn_present_path_rotation.md">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

