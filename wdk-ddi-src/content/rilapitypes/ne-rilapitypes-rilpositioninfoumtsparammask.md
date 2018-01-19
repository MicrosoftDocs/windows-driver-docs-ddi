---
UID: NE:rilapitypes.RILPOSITIONINFOUMTSPARAMMASK
title: RILPOSITIONINFOUMTSPARAMMASK
author: windows-driver-content
description: This enumeration describes the RILPOSITIONINFOUMTSPARAMMASK.
old-location: netvista\rilpositioninfoumtsparammask.htm
old-project: netvista
ms.assetid: fde2eb3f-ea12-45e6-93d1-7bdb0ea8c6b2
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILPOSITIONINFOUMTSPARAMMASK, RILPOSITIONINFOUMTSPARAMMASK
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
req.alt-api: RILPOSITIONINFOUMTSPARAMMASK
req.alt-loc: rilapitypes.h
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
req.typenames: RILPOSITIONINFOUMTSPARAMMASK
req.product: Windows 10 or later.
---

# RILPOSITIONINFOUMTSPARAMMASK enumeration



## -description

## -syntax

````
enum RILPOSITIONINFOUMTSPARAMMASK {
  RIL_PARAM_POSITION_UMTS_MCC          = 0x00000001, 
  RIL_PARAM_POSITION_UMTS_MNC          = 0x00000002, 
  RIL_PARAM_POSITION_UMTS_LAC          = 0x00000004, 
  RIL_PARAM_POSITION_UMTS_CELLID       = 0x00000008, 
  RIL_PARAM_POSITION_UMTS_FREQINFO_UL  = 0x00000010, 
  RIL_PARAM_POSITION_UMTS_FREQINFO_DL  = 0x00000020, 
  RIL_PARAM_POSITION_UMTS_FREQINFO_NT  = 0x00000040, 
   RIL_PARAM_POSITION_UMTS_UARFCN      = 0x00000080, 
  RIL_PARAM_POSITION_UMTS_PRIMARY_SC   = 0x00000100, 
  RIL_PARAM_POSITION_UMTS_RSCP         = 0x00000200, 
  RIL_PARAM_POSITION_UMTS_ECNO         = 0x00000400, 
  RIL_PARAM_POSITION_UMTS_PATHLOSS     = 0x00000800, 
  RIL_PARAM_POSITION_UMTS_ALL          = 0x00000fff 

};
````


## -enum-fields

### -field RIL_PARAM_POSITION_UMTS_MCC


### -field RIL_PARAM_POSITION_UMTS_MNC


### -field RIL_PARAM_POSITION_UMTS_LAC


### -field RIL_PARAM_POSITION_UMTS_CELLID


### -field RIL_PARAM_POSITION_UMTS_FREQINFO_UL


### -field RIL_PARAM_POSITION_UMTS_FREQINFO_DL


### -field RIL_PARAM_POSITION_UMTS_FREQINFO_NT


### -field  RIL_PARAM_POSITION_UMTS_UARFCN


### -field RIL_PARAM_POSITION_UMTS_PRIMARY_SC


### -field RIL_PARAM_POSITION_UMTS_RSCP


### -field RIL_PARAM_POSITION_UMTS_ECNO


### -field RIL_PARAM_POSITION_UMTS_PATHLOSS


### -field RIL_PARAM_POSITION_UMTS_ALL


## -remarks
Networks will vary, but the following table summarizes which items are returned for common UMTS networks. 

<b>Serving network</b>

MobileCountryCode

Yes

0 through 999



MobileNetworkCode

LocationAreaCode

0 through 65,535

CellID

0 through 268,435,455

28 bits; may not always be available

FrequencyInfoUL

No

FrequencyInfoDL

FrequencyInfoNT

UARFCN

0 through 16,383

UTRA absolute channel number

PrimaryScramblingCode

0 through 511

RSCP

−25 through −120

 Measured in dBm; defined in 25.304

ECNO

0 through −50

 Measured in dB   

PathLoss

<b>UMTS neighbors</b> (subject to availability from network)

May not always be available; CellID may not be valid in DCH state

WCDMA layer frequency

–25 through −120


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILPOSITIONINFOUMTSPARAMMASK enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

