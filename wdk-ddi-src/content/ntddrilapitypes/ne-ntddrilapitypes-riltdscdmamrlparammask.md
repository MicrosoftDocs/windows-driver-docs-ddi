---
UID: NE:ntddrilapitypes.RILTDSCDMAMRLPARAMMASK
title: RILTDSCDMAMRLPARAMMASK (ntddrilapitypes.h)
description: This enumeration describes the RILTDSCDMAMRLPARAMMASK.
old-location: netvista\riltdscdmamrlparammask.htm
tech.root: netvista
ms.assetid: d2cc4c39-b96e-4078-bfea-2e06a07e938e
ms.date: 02/16/2018
ms.keywords: RILTDSCDMAMRLPARAMMASK, RILTDSCDMAMRLPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_TDSCDMAMRL_ALL, RIL_PARAM_TDSCDMAMRL_CELLID, RIL_PARAM_TDSCDMAMRL_CELLPARAM, RIL_PARAM_TDSCDMAMRL_LAC, RIL_PARAM_TDSCDMAMRL_MCC, RIL_PARAM_TDSCDMAMRL_MNC, RIL_PARAM_TDSCDMAMRL_PATHLOSS, RIL_PARAM_TDSCDMAMRL_RSCP, RIL_PARAM_TDSCDMAMRL_UARFCN, netvista.riltdscdmamrlparammask, rilapitypes/RILTDSCDMAMRLPARAMMASK, rilapitypes/RIL_PARAM_TDSCDMAMRL_ALL, rilapitypes/RIL_PARAM_TDSCDMAMRL_CELLID, rilapitypes/RIL_PARAM_TDSCDMAMRL_CELLPARAM, rilapitypes/RIL_PARAM_TDSCDMAMRL_LAC, rilapitypes/RIL_PARAM_TDSCDMAMRL_MCC, rilapitypes/RIL_PARAM_TDSCDMAMRL_MNC, rilapitypes/RIL_PARAM_TDSCDMAMRL_PATHLOSS, rilapitypes/RIL_PARAM_TDSCDMAMRL_RSCP, rilapitypes/RIL_PARAM_TDSCDMAMRL_UARFCN
ms.topic: enum
req.header: ntddrilapitypes.h
req.include-header: Rilapitypes.h, Ntddrilapitypes.h
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
-	rilapitypes.h
api_name:
-	RILTDSCDMAMRLPARAMMASK
product:
- Windows
targetos: Windows
req.typenames: RILTDSCDMAMRLPARAMMASK
---

# RILTDSCDMAMRLPARAMMASK enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILTDSCDMAMRLPARAMMASK.




## -syntax


```cpp
enum RILTDSCDMAMRLPARAMMASK {
  RIL_PARAM_TDSCDMAMRL_MCC        = 0x00000001,
  RIL_PARAM_TDSCDMAMRL_MNC        = 0x00000002,
  RIL_PARAM_TDSCDMAMRL_LAC        = 0x00000004,
  RIL_PARAM_TDSCDMAMRL_CELLID     = 0x00000008,
  RIL_PARAM_TDSCDMAMRL_UARFCN     = 0x00000010,
  RIL_PARAM_TDSCDMAMRL_CELLPARAM  = 0x00000020,
  RIL_PARAM_TDSCDMAMRL_RSCP       = 0x00000040,
  RIL_PARAM_TDSCDMAMRL_PATHLOSS   = 0x00000080,
  RIL_PARAM_TDSCDMAMRL_ALL        = 0x000000ff

};
```


## -enum-fields




### -field RIL_PARAM_TDSCDMAMRL_MCC


### -field RIL_PARAM_TDSCDMAMRL_MNC


### -field RIL_PARAM_TDSCDMAMRL_LAC


### -field RIL_PARAM_TDSCDMAMRL_CELLID


### -field RIL_PARAM_TDSCDMAMRL_UARFCN


### -field RIL_PARAM_TDSCDMAMRL_CELLPARAM


### -field RIL_PARAM_TDSCDMAMRL_RSCP


### -field RIL_PARAM_TDSCDMAMRL_PATHLOSS


### -field RIL_PARAM_TDSCDMAMRL_ALL


## -remarks



Networks will vary, but the following table summarizes which items are returned for typical TD-SCDMA networks.

<b>Serving network</b>

<table>
<tr>
<th>Entry</th>
<th>Typically returned?</th>
<th>Range</th>
<th>Comment</th>
</tr>
<tr>
<td>
MobileCountryCode

</td>
<td>
Yes

</td>
<td>
0 through 999

</td>
<td>


</td>
</tr>
<tr>
<td>
MobileNetworkCode

</td>
<td>
Yes

</td>
<td>
0 through 999

</td>
<td>


</td>
</tr>
<tr>
<td>
LocationAreaCode

</td>
<td>
Yes

</td>
<td>
0 to 65535

</td>
<td>


</td>
</tr>
<tr>
<td>
CellID

</td>
<td>
Yes

</td>
<td>
0 through 268,435,455

</td>
<td>
May not always be available; 28 bits

</td>
</tr>
<tr>
<td>
UARFCN

</td>
<td>
Yes

</td>
<td>
0 through 16,383

</td>
<td>
Channel number

</td>
</tr>
<tr>
<td>
CellParameterID

</td>
<td>
Yes

</td>
<td>
0 through 127

</td>
<td>


</td>
</tr>
<tr>
<td>
TimingAdvance

</td>
<td>
Yes

</td>
<td>
0 through 8,191

</td>
<td>
By standards, the maximum range is 96 chips (0 to 96x8)

</td>
</tr>
<tr>
<td>
RSCP

</td>
<td>
Yes

</td>
<td>
−25 through −128

</td>
<td>
Received signal code power of serving cell in dBm

</td>
</tr>
<tr>
<td>
PathLoss

</td>
<td>
No

</td>
<td>
46 through 158

</td>
<td>
Path loss of serving cell in dBs

</td>
</tr>
</table>
 

<b>TD-SCDMA neighbors</b> (subject to availability from network)

<table>
<tr>
<th>Entry</th>
<th>Typically returned?</th>
<th>Range</th>
<th>Comment</th>
</tr>
<tr>
<td>
MobileCountryCode

</td>
<td>
No

</td>
<td>


</td>
<td>


</td>
</tr>
<tr>
<td>
MobileNetworkCode

</td>
<td>
No

</td>
<td>


</td>
<td>


</td>
</tr>
<tr>
<td>
LocationAreaCode

</td>
<td>
No

</td>
<td>


</td>
<td>


</td>
</tr>
<tr>
<td>
CellID

</td>
<td>
No

</td>
<td>


</td>
<td>


</td>
</tr>
<tr>
<td>
UARFCN

</td>
<td>
Yes

</td>
<td>
0 through 16,383

</td>
<td>
Channel number

</td>
</tr>
<tr>
<td>
CellParameterID

</td>
<td>
Yes

</td>
<td>
0 through 127

</td>
<td>


</td>
</tr>
<tr>
<td>
TimingAdvance

</td>
<td>
No

</td>
<td>


</td>
<td>


</td>
</tr>
<tr>
<td>
RSCP

</td>
<td>
Yes

</td>
<td>
−25 through −128

</td>
<td>
Received signal code power of serving cell in dBm

</td>
</tr>
<tr>
<td>
PathLoss

</td>
<td>
No

</td>
<td>


</td>
<td>


</td>
</tr>
</table>
 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>



 

 


