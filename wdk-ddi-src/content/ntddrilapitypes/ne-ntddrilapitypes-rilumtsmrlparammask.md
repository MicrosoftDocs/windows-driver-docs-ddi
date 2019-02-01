---
UID: NE:ntddrilapitypes.RILUMTSMRLPARAMMASK
title: RILUMTSMRLPARAMMASK (ntddrilapitypes.h)
description: This enumeration describes the RILUMTSMRLPARAMMASK.
old-location: netvista\rilumtsmrlparammask.htm
tech.root: netvista
ms.assetid: ba1f48ab-f301-4ae8-b56e-92eb6e3601f2
ms.date: 02/16/2018
ms.keywords: RILUMTSMRLPARAMMASK, RILUMTSMRLPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_UMTSMRL_ALL, RIL_PARAM_UMTSMRL_CELLID, RIL_PARAM_UMTSMRL_ECNO, RIL_PARAM_UMTSMRL_LAC, RIL_PARAM_UMTSMRL_MCC, RIL_PARAM_UMTSMRL_MNC, RIL_PARAM_UMTSMRL_PATHLOSS, RIL_PARAM_UMTSMRL_PRIMARY_SC, RIL_PARAM_UMTSMRL_RSCP, RIL_PARAM_UMTSMRL_UARFCN, netvista.rilumtsmrlparammask, rilapitypes/RILUMTSMRLPARAMMASK, rilapitypes/RIL_PARAM_UMTSMRL_ALL, rilapitypes/RIL_PARAM_UMTSMRL_CELLID, rilapitypes/RIL_PARAM_UMTSMRL_ECNO, rilapitypes/RIL_PARAM_UMTSMRL_LAC, rilapitypes/RIL_PARAM_UMTSMRL_MCC, rilapitypes/RIL_PARAM_UMTSMRL_MNC, rilapitypes/RIL_PARAM_UMTSMRL_PATHLOSS, rilapitypes/RIL_PARAM_UMTSMRL_PRIMARY_SC, rilapitypes/RIL_PARAM_UMTSMRL_RSCP, rilapitypes/RIL_PARAM_UMTSMRL_UARFCN
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
-	RILUMTSMRLPARAMMASK
product:
- Windows
targetos: Windows
req.typenames: RILUMTSMRLPARAMMASK
---

# RILUMTSMRLPARAMMASK enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILUMTSMRLPARAMMASK.


## -syntax


```cpp
enum RILUMTSMRLPARAMMASK  {
  RIL_PARAM_UMTSMRL_MCC         = 0x00000001,
  RIL_PARAM_UMTSMRL_MNC         = 0x00000002,
  RIL_PARAM_UMTSMRL_LAC         = 0x00000004,
  RIL_PARAM_UMTSMRL_CELLID      = 0x00000008,
  RIL_PARAM_UMTSMRL_UARFCN      =  0x00000010,
  RIL_PARAM_UMTSMRL_PRIMARY_SC  =  0x00000020,
  RIL_PARAM_UMTSMRL_RSCP        = 0x00000040,
  RIL_PARAM_UMTSMRL_ECNO        = 0x00000080,
  RIL_PARAM_UMTSMRL_PATHLOSS    = 0x00000100,
  RIL_PARAM_UMTSMRL_ALL         = 0x000001ff

};
```


## -enum-fields




### -field RIL_PARAM_UMTSMRL_MCC


### -field RIL_PARAM_UMTSMRL_MNC


### -field RIL_PARAM_UMTSMRL_LAC


### -field RIL_PARAM_UMTSMRL_CELLID


### -field RIL_PARAM_UMTSMRL_UARFCN


### -field RIL_PARAM_UMTSMRL_PRIMARY_SC


### -field RIL_PARAM_UMTSMRL_RSCP


### -field RIL_PARAM_UMTSMRL_ECNO


### -field RIL_PARAM_UMTSMRL_PATHLOSS


### -field RIL_PARAM_UMTSMRL_ALL


## -remarks



Networks will vary, but the following table summarizes which items are returned for common UMTS networks.

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
0 through 65,535

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
28 bits; may not always be available

</td>
</tr>
<tr>
<td>
FrequencyInfoUL

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
FrequencyInfoDL

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
FrequencyInfoNT

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
UTRA absolute channel number

</td>
</tr>
<tr>
<td>
PrimaryScramblingCode

</td>
<td>
Yes

</td>
<td>
0 through 511

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
−25 through −120

</td>
<td>
 Measured in dBm; defined in 25.304

</td>
</tr>
<tr>
<td>
ECNO

</td>
<td>
Yes

</td>
<td>
0 through −50

</td>
<td>
 Measured in dB

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
 

<b>UMTS neighbors</b> (subject to availability from network)

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
May not always be available; CellID may not be valid in DCH state

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
WCDMA layer frequency

</td>
</tr>
<tr>
<td>
PrimaryScramblingCode

</td>
<td>
Yes

</td>
<td>
0 through 511

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
–25 through −120

</td>
<td>
 Measured in dBm; defined in 25.304

</td>
</tr>
<tr>
<td>
ECNO

</td>
<td>
Yes

</td>
<td>
0 through −50

</td>
<td>
 Measured in dB

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



 

 


