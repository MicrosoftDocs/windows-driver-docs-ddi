---
UID: NF:d3dkmdt.D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART
title: D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART function (d3dkmdt.h)
description: A helper function that extracts the rotation angle from a given value of the D3DKMDT_VIDPN_PRESENT_PATH_ROTATION enumeration.
old-location: display\d3dkmdt_vppr_get_content_rotation_part.htm
tech.root: display
ms.assetid: B533B0DD-B72C-4294-8E88-4C15EA1BB16E
ms.date: 05/10/2018
ms.keywords: D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART, D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART function [Display Devices], d3dkmdt/D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART, display.d3dkmdt_vppr_get_content_rotation_part
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- D3dkmdt.h
api_name:
- D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART
product:
- Windows
targetos: Windows
req.typenames: 
---

# D3DKMDT_VPPR_GET_CONTENT_ROTATION_PART function


## -description


A helper function that extracts the rotation angle from a given value of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546700">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION</a> enumeration. Only drivers that support path-independent rotation (DXGKDDI_INTERFACE_VERSION &gt;= DXGKDDI_INTERFACE_VERSION_WDDM1_3_PATH_INDEPENDENT_ROTATION) should call this function.


## -parameters




### -param Rotation

On input, a value from  the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546700">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION</a> enumeration.

On output, a value between 1 and 4, inclusive, that corresponds to the <b>ROTATION</b> portion of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546700">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION</a> constant values. An output value of 1 (identity) represents 0 degrees of rotation, 2 represents 90 degrees, and so on. An output value of 0 indicates that the VidPN path is not initialized.


## -returns



The returned value corresponds to the rotation angle as follows:

|Input enumeration value|Input enumeration constant|Rotation in degrees|Output Rotation value|
|--- |--- |--- |--- |
|0|D3DKMDT_VPPR_UNINITIALIZED|-|0|
|1|D3DKMDT_VPPR_IDENTITY|0|1|
|2|D3DKMDT_VPPR_ROTATE90|90|2|
|3|D3DKMDT_VPPR_ROTATE180|180|3|
|4|D3DKMDT_VPPR_ROTATE270|270|4|
|5|D3DKMDT_VPPR_IDENTITY_OFFSET90|0|1|
|6|D3DKMDT_VPPR_ROTATE90_OFFSET90|90|2|
|7|D3DKMDT_VPPR_ROTATE180_OFFSET90|180|3|
|8|D3DKMDT_VPPR_ROTATE270_OFFSET90|270|4|
|9|D3DKMDT_VPPR_IDENTITY_OFFSET180|0|1|
|10|D3DKMDT_VPPR_ROTATE90_OFFSET180|90|2|
|11|D3DKMDT_VPPR_ROTATE180_OFFSET180|180|3|
|12|D3DKMDT_VPPR_ROTATE270_OFFSET180|270|4|
|13|D3DKMDT_VPPR_IDENTITY_OFFSET270|0|1|
|14|D3DKMDT_VPPR_ROTATE90_OFFSET270|90|2|
|15|D3DKMDT_VPPR_ROTATE180_OFFSET270|180|3|
|16|D3DKMDT_VPPR_ROTATE270_OFFSET270|270|4|


## -remarks



This function is declared inline in D3dkmdt.h as:

```cpp
__inline
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
}
```

Your driver typically won't need to call this function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546700">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION</a>
 

 

