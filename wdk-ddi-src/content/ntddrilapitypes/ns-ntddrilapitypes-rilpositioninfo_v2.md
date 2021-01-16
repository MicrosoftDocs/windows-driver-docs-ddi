---
UID: NS:ntddrilapitypes.RILPOSITIONINFO_V2
title: RILPOSITIONINFO_V2 (ntddrilapitypes.h)
description: This structure represents the RILPOSITIONINFO_V2.
old-location: netvista\rilpositioninfo_v2.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["RILPOSITIONINFO_V2 structure"]
ms.keywords: "*LPRILPOSITIONINFO, *LPRILPOSITIONINFO_V2, RILPOSITIONINFO, RILPOSITIONINFO_V2, RILPOSITIONINFO_V2 structure [Network Drivers Starting with Windows Vista], netvista.rilpositioninfo_v2, rilapitypes/RILPOSITIONINFO_V2"
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
req.typenames: RILPOSITIONINFO_V2, *LPRILPOSITIONINFO_V2, RILPOSITIONINFO, *LPRILPOSITIONINFO
f1_keywords:
 - RILPOSITIONINFO_V2
 - ntddrilapitypes/RILPOSITIONINFO_V2
 - LPRILPOSITIONINFO_V2
 - ntddrilapitypes/LPRILPOSITIONINFO_V2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILPOSITIONINFO_V2
 - LPRILPOSITIONINFO_V2
---

# RILPOSITIONINFO_V2 structure (ntddrilapitypes.h)


## -description

<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents the RILPOSITIONINFO_V2.

## -struct-fields

### -field cbSize

The size of the structure in bytes.

### -field dwSystemType

Indicates the system type or types for which serving cell information is valid, a bitmask of one or more <a href="..\rilapitypes\ne-rilapitypes-rilsystemtype.md">RILSYSTEMTYPE</a> values. For example, on an SVLTE system, this could be <code>RIL_SYSTEMTYPE_LTE|RIL_SYSTEMTYPE_1XRTT</code>, indicating that both the CDMA cell information (including serving cell(s)) in <b>rc2kMRL</b> and <b>stLTEServingCellInfo</b> are valid.

### -field stGSMServingCellInfo

GSM serving cell information, a <a href="..\rilapitypes\ns-rilapitypes-rilpositioninfogsm.md">RILPOSITIONINFOGSM</a> struct.

### -field stUMTSServingCellInfo

UMTS serving cell information, a <a href="..\rilapitypes\ns-rilapitypes-rilpositioninfoumts.md">RILPOSITIONINFOUMTS</a> struct.

### -field stTDSCDMAServingCellInfo

TD-SCDMA serving cell information, a <a href="..\rilapitypes\ns-rilapitypes-rilpositioninfotdscdma.md">RILPOSITIONINFOTDSCDMA</a> struct. This field is not present in <a href="/previous-versions/windows/hardware/cellular/dn931134(v=vs.85)">RILPOSITIONINFO_V1</a>.

### -field stLTEServingCellInfo

LTE serving cell information, a <a href="..\rilapitypes\ns-rilapitypes-rilpositioninfolte.md">RILPOSITIONINFOLTE</a> struct.

### -field dwCntGSMNMR

The number of GSM network measurement reports in <b>rgNMR</b>.

### -field rgNMR

GSM network measurement reports, an array of <a href="..\rilapitypes\ns-rilapitypes-rilgsmnmr.md">RILGSMNMR</a> structs.

### -field dwCntUMTSMRL

The number of entries in the UMTS measured results list <b>ruMRL</b>.

### -field ruMRL

### -field dwCntTDSCDMAMRL

The number of entries in the TD-SCDMA measured results list <b>rtMRL</b>. This field is not present in RILPOSITIONINFO_V1.

### -field rtMRL

### -field dwCntEUTRAMRL

The number of entries in the EUTRAN (LTE) measured results list <b>reMRL</b>.

### -field reMRL

E-UTRAN (LTE) measured results list, an array of <a href="..\rilapitypes\ns-rilapitypes-rileutramrl.md">RILEUTRAMRL</a> structs.

### -field dwCntC2KMRL

The number of entries in the cdma2000 measured results list <b>rc2kMRL</b>.

### -field rc2kMRL

The cdma2000 measured results list, an array of <a href="..\rilapitypes\ns-rilapitypes-rilc2kmrl.md">RILC2KMRL</a> structs.


#### - RILTDSCDMAMRL

TD-SCDMA measured results list, an array of <a href="..\rilapitypes\ns-rilapitypes-riltdscdmamrl.md">RILTDSCDMAMRL</a> structs. This field is not present in RILPOSITIONINFO_V1.


#### - RILUMTSMRL

UMTS measured results list, an array of <a href="..\rilapitypes\ns-rilapitypes-rilumtsmrl.md">RILUMTSMRL</a> structs.

## -syntax

```cpp
struct RILPOSITIONINFO_V2 {
  DWORD                  cbSize;
  DWORD                  dwSystemType;
  RILPOSITIONINFOGSM     stGSMServingCellInfo;
  RILPOSITIONINFOUMTS    stUMTSServingCellInfo;
  RILPOSITIONINFOTDSCDMA stTDSCDMAServingCellInfo;
  RILPOSITIONINFOLTE     stLTEServingCellInfo;
  DWORD                  dwCntGSMNMR;
  RILGSMNMR              rgNMR[MAX_GSMPOS_COUNT_OF_NMR];
  DWORD                  dwCntUMTSMRL;
  ruMRL                  RILUMTSMRL[MAX_UMTSPOS_COUNT_OF_MRL];
  DWORD                  dwCntTDSCDMAMRL;
  rtMRL                  RILTDSCDMAMRL[MAX_TDSCDMAPOS_COUNT_OF_MRL];
  DWORD                  dwCntEUTRAMRL;
  RILEUTRAMRL            reMRL[MAX_EUTRAPOS_COUNT_OF_MRL];
  DWORD                  dwCntC2KMRL;
  RILC2KMRL              rc2kMRL[MAX_C2KPOS_COUNT_OF_MRL];
};
```

## -see-also

<a href="/previous-versions/windows/hardware/cellular/dn946511(v=vs.85)">Cellular COM structures</a>

