---
UID: NE:ntddrilapitypes.RILEUTRAMRLPARAMMASK
title: RILEUTRAMRLPARAMMASK (ntddrilapitypes.h)
description: This enumeration describes the RILEUTRAMRLPARAMMASK.
old-location: netvista\rileutramrlparammask.htm
tech.root: netvista
ms.assetid: 555dd967-ea38-45fa-8e7f-5318ca5c6dd2
ms.date: 02/16/2018
keywords: ["RILEUTRAMRLPARAMMASK enumeration"]
ms.keywords: RILEUTRAMRLPARAMMASK, RILEUTRAMRLPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_EUTRAMRL_ALL, RIL_PARAM_EUTRAMRL_CELLID, RIL_PARAM_EUTRAMRL_EARFCN, RIL_PARAM_EUTRAMRL_MCC, RIL_PARAM_EUTRAMRL_MNC, RIL_PARAM_EUTRAMRL_PHYSCELLID, RIL_PARAM_EUTRAMRL_RSRP, RIL_PARAM_EUTRAMRL_RSRQ, RIL_PARAM_EUTRAMRL_TAC, netvista.rileutramrlparammask, rilapitypes/RILEUTRAMRLPARAMMASK, rilapitypes/RIL_PARAM_EUTRAMRL_ALL, rilapitypes/RIL_PARAM_EUTRAMRL_CELLID, rilapitypes/RIL_PARAM_EUTRAMRL_EARFCN, rilapitypes/RIL_PARAM_EUTRAMRL_MCC, rilapitypes/RIL_PARAM_EUTRAMRL_MNC, rilapitypes/RIL_PARAM_EUTRAMRL_PHYSCELLID, rilapitypes/RIL_PARAM_EUTRAMRL_RSRP, rilapitypes/RIL_PARAM_EUTRAMRL_RSRQ, rilapitypes/RIL_PARAM_EUTRAMRL_TAC
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
targetos: Windows
req.typenames: RILEUTRAMRLPARAMMASK
f1_keywords:
 - RILEUTRAMRLPARAMMASK
 - ntddrilapitypes/RILEUTRAMRLPARAMMASK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILEUTRAMRLPARAMMASK
---

# RILEUTRAMRLPARAMMASK enumeration (ntddrilapitypes.h)


## -description

<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILEUTRAMRLPARAMMASK.

## -enum-fields

### -field RIL_PARAM_EUTRAMRL_MCC

### -field RIL_PARAM_EUTRAMRL_MNC

### -field RIL_PARAM_EUTRAMRL_CELLID

### -field RIL_PARAM_EUTRAMRL_EARFCN

### -field RIL_PARAM_EUTRAMRL_PHYSCELLID

### -field RIL_PARAM_EUTRAMRL_TAC

### -field RIL_PARAM_EUTRAMRL_RSRP

### -field RIL_PARAM_EUTRAMRL_RSRQ

### -field RIL_PARAM_EUTRAMRL_ALL

## -syntax

```cpp
enum RILEUTRAMRLPARAMMASK {
  RIL_PARAM_EUTRAMRL_MCC         = 0x00000001,
  RIL_PARAM_EUTRAMRL_MNC         = 0x00000002,
  RIL_PARAM_EUTRAMRL_CELLID      = 0x00000004,
  RIL_PARAM_EUTRAMRL_EARFCN      = 0x00000008,
  RIL_PARAM_EUTRAMRL_PHYSCELLID  = 0x00000010,
  RIL_PARAM_EUTRAMRL_TAC         = 0x00000020,
  RIL_PARAM_EUTRAMRL_RSRP        = 0x00000040,
  RIL_PARAM_EUTRAMRL_RSRQ        = 0x00000080,
  RIL_PARAM_EUTRAMRL_ALL         = 0x000000ff

};
```

## -remarks

Networks will vary, but the following table summarizes which items are returned for typical LTE networks.

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
CellID

</td>
<td>
Yes

</td>
<td>
0 through 268,435,455

</td>
<td>
Global cell ID in the system information block; 28 bits

</td>
</tr>
<tr>
<td>
EARFCN

</td>
<td>
Yes

</td>
<td>
0 through 65,535

</td>
<td>
E-UTRA absolute radio frequency channel number of the serving cell

</td>
</tr>
<tr>
<td>
PhysCellID

</td>
<td>
Yes

</td>
<td>
0 through 503

</td>
<td>
LTE serving cell ID

</td>
</tr>
<tr>
<td>
TAC

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
RSRP

</td>
<td>
Yes

</td>
<td>
−44 through −140

</td>
<td>
The current reference signal receive power in dBm

</td>
</tr>
<tr>
<td>
RSRQ

</td>
<td>
Yes

</td>
<td>
−3 through −20

</td>
<td>
Measured in dB

</td>
</tr>
</table>
 

<b>LTE neighbors</b> (subject to availability from network)

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
EARFCN

</td>
<td>
Yes

</td>
<td>
0 through 65,535

</td>
<td>
E-UTRA absolute radio frequency channel number of the serving cell

</td>
</tr>
<tr>
<td>
PhysCellID

</td>
<td>
Yes

</td>
<td>
0 through 503

</td>
<td>
LTE serving cell ID

</td>
</tr>
<tr>
<td>
TAC

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
RSRP

</td>
<td>
Yes

</td>
<td>
−44 through −140

</td>
<td>
The current reference signal receive power in dBm

</td>
</tr>
<tr>
<td>
RSRQ

</td>
<td>
Yes

</td>
<td>
−3 through −20

</td>
<td>
Measured in dB

</td>
</tr>
</table>

## -see-also

<a href="/previous-versions/windows/hardware/cellular/dn946509(v=vs.85)">Cellular COM enumerations</a>