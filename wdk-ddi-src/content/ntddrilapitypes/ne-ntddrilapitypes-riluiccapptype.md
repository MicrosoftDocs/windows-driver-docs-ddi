---
UID: NE:ntddrilapitypes.RILUICCAPPTYPE
title: RILUICCAPPTYPE
author: windows-driver-content
description: This enumeration describes the RILUICCAPPTYPE.
old-location: netvista\riluiccapptype.htm
tech.root: netvista
ms.assetid: cba1fcc3-74d0-44b7-b480-3e7d754f9efe
ms.date: 2/16/2018
ms.keywords: RILUICCAPPTYPE, RILUICCAPPTYPE enumeration [Network Drivers Starting with Windows Vista], RIL_UICCAPPTYPE_CSIM, RIL_UICCAPPTYPE_ISIM, RIL_UICCAPPTYPE_MF, RIL_UICCAPPTYPE_MF_RUIM, RIL_UICCAPPTYPE_MF_SIM, RIL_UICCAPPTYPE_UNKNOWN, RIL_UICCAPPTYPE_USIM, netvista.riluiccapptype, rilapitypes/RILUICCAPPTYPE, rilapitypes/RIL_UICCAPPTYPE_CSIM, rilapitypes/RIL_UICCAPPTYPE_ISIM, rilapitypes/RIL_UICCAPPTYPE_MF, rilapitypes/RIL_UICCAPPTYPE_MF_RUIM, rilapitypes/RIL_UICCAPPTYPE_MF_SIM, rilapitypes/RIL_UICCAPPTYPE_UNKNOWN, rilapitypes/RIL_UICCAPPTYPE_USIM
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
-	RILUICCAPPTYPE
product:
- Windows
targetos: Windows
req.typenames: RILUICCAPPTYPE
---

# RILUICCAPPTYPE enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILUICCAPPTYPE.


## -syntax


```
enum RILUICCAPPTYPE {
  RIL_UICCAPPTYPE_UNKNOWN  = 0x00000001,
  RIL_UICCAPPTYPE_MF       = 0x00000002,
  RIL_UICCAPPTYPE_MF_SIM   = 0x00000003,
  RIL_UICCAPPTYPE_MF_RUIM  = 0x00000004,
  RIL_UICCAPPTYPE_USIM     = 0x00000005,
  RIL_UICCAPPTYPE_CSIM     = 0x00000006,
  RIL_UICCAPPTYPE_ISIM     = 0x00000007

};
```


## -enum-fields




### -field RIL_UICCAPPTYPE_UNKNOWN


### -field RIL_UICCAPPTYPE_MF


### -field RIL_UICCAPPTYPE_MF_SIM


### -field RIL_UICCAPPTYPE_MF_RUIM


### -field RIL_UICCAPPTYPE_USIM


### -field RIL_UICCAPPTYPE_CSIM


### -field RIL_UICCAPPTYPE_ISIM


### -field RIL_UICCAPPTYPE_MAX




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



 

 


