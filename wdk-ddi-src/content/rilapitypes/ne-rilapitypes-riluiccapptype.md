---
UID: NE:rilapitypes.RILUICCAPPTYPE
title: RILUICCAPPTYPE
author: windows-driver-content
description: This enumeration describes the RILUICCAPPTYPE.
old-location: netvista\riluiccapptype.htm
old-project: netvista
ms.assetid: cba1fcc3-74d0-44b7-b480-3e7d754f9efe
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RIL_UICCAPPTYPE_MF_RUIM, RIL_UICCAPPTYPE_CSIM, RIL_UICCAPPTYPE_USIM, rilapitypes/RIL_UICCAPPTYPE_MF_SIM, rilapitypes/RIL_UICCAPPTYPE_CSIM, rilapitypes/RIL_UICCAPPTYPE_USIM, rilapitypes/RIL_UICCAPPTYPE_ISIM, RIL_UICCAPPTYPE_ISIM, rilapitypes/RIL_UICCAPPTYPE_MF, RILUICCAPPTYPE enumeration [Network Drivers Starting with Windows Vista], RIL_UICCAPPTYPE_MF_SIM, RIL_UICCAPPTYPE_MF_RUIM, RILUICCAPPTYPE, RIL_UICCAPPTYPE_MF, netvista.riluiccapptype, RIL_UICCAPPTYPE_UNKNOWN, rilapitypes/RIL_UICCAPPTYPE_UNKNOWN, rilapitypes/RILUICCAPPTYPE
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
-	RILUICCAPPTYPE
product: Windows
targetos: Windows
req.typenames: RILUICCAPPTYPE
req.product: Windows 10 or later.
---

# RILUICCAPPTYPE enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILUICCAPPTYPE.


## -syntax


````
enum RILUICCAPPTYPE {
  RIL_UICCAPPTYPE_UNKNOWN  = 0x00000001, 
  RIL_UICCAPPTYPE_MF       = 0x00000002, 
  RIL_UICCAPPTYPE_MF_SIM   = 0x00000003, 
  RIL_UICCAPPTYPE_MF_RUIM  = 0x00000004, 
  RIL_UICCAPPTYPE_USIM     = 0x00000005, 
  RIL_UICCAPPTYPE_CSIM     = 0x00000006, 
  RIL_UICCAPPTYPE_ISIM     = 0x00000007 

};
````


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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILUICCAPPTYPE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

