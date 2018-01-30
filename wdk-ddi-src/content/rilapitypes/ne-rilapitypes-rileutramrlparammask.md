---
UID: NE:rilapitypes.RILEUTRAMRLPARAMMASK
title: RILEUTRAMRLPARAMMASK
author: windows-driver-content
description: This enumeration describes the RILEUTRAMRLPARAMMASK.
old-location: netvista\rileutramrlparammask.htm
old-project: netvista
ms.assetid: 555dd967-ea38-45fa-8e7f-5318ca5c6dd2
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RIL_PARAM_EUTRAMRL_RSRQ, RILEUTRAMRLPARAMMASK, rilapitypes/RIL_PARAM_EUTRAMRL_MNC, rilapitypes/RIL_PARAM_EUTRAMRL_EARFCN, RIL_PARAM_EUTRAMRL_ALL, rilapitypes/RILEUTRAMRLPARAMMASK, rilapitypes/RIL_PARAM_EUTRAMRL_MCC, RIL_PARAM_EUTRAMRL_RSRQ, rilapitypes/RIL_PARAM_EUTRAMRL_ALL, rilapitypes/RIL_PARAM_EUTRAMRL_CELLID, rilapitypes/RIL_PARAM_EUTRAMRL_TAC, netvista.rileutramrlparammask, rilapitypes/RIL_PARAM_EUTRAMRL_RSRP, RIL_PARAM_EUTRAMRL_RSRP, RIL_PARAM_EUTRAMRL_PHYSCELLID, RIL_PARAM_EUTRAMRL_MCC, rilapitypes/RIL_PARAM_EUTRAMRL_PHYSCELLID, RIL_PARAM_EUTRAMRL_MNC, RIL_PARAM_EUTRAMRL_CELLID, RILEUTRAMRLPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_EUTRAMRL_TAC, RIL_PARAM_EUTRAMRL_EARFCN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILEUTRAMRLPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILEUTRAMRLPARAMMASK
req.product: Windows 10 or later.
---

# RILEUTRAMRLPARAMMASK enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILEUTRAMRLPARAMMASK.




## -syntax


````
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
````


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

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILEUTRAMRLPARAMMASK enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

