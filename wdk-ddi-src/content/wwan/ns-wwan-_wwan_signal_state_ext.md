---
UID: NS:wwan._WWAN_SIGNAL_STATE_EXT
title: _WWAN_SIGNAL_STATE_EXT (wwan.h)
description: The WWAN_SIGNAL_STATE_EXT structure represents an extension to the signal state of the MB device.
tech.root: netvista
ms.assetid: 575B91C4-FF8A-488B-A12E-2DB13FE6C900
ms.date: 04/05/2019
keywords: ["WWAN_SIGNAL_STATE_EXT structure"]
ms.keywords: "*PWWAN_SIGNAL_STATE_EXT, PWWAN_SIGNAL_STATE_EXT, PWWAN_SIGNAL_STATE_EXT structure pointer [Network Drivers Starting with Windows Vista], WWAN_SIGNAL_STATE_EXT, WWAN_SIGNAL_STATE_EXT structure [Network Drivers Starting with Windows Vista], WwanRef_6a92457b-8b82-4956-9dce-98e5aeec9091.xml, _WWAN_SIGNAL_STATE_EXT, netvista.wwan_signal_state_EXT, wwan/PWWAN_SIGNAL_STATE_EXT, wwan/WWAN_SIGNAL_STATE_EXT"
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1903
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
req.typenames: WWAN_SIGNAL_STATE_EXT, *PWWAN_SIGNAL_STATE_EXT
f1_keywords:
 - _WWAN_SIGNAL_STATE_EXT
 - wwan/_WWAN_SIGNAL_STATE_EXT
 - PWWAN_SIGNAL_STATE_EXT
 - wwan/PWWAN_SIGNAL_STATE_EXT
 - WWAN_SIGNAL_STATE_EXT
 - wwan/WWAN_SIGNAL_STATE_EXT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - WWAN_SIGNAL_STATE_EXT
---

# _WWAN_SIGNAL_STATE_EXT structure


## -description

The **WWAN_SIGNAL_STATE_EXT** structure represents an extension to the signal state of the MB device. In Windows 10, version 1903 and later, [**WWAN_SIGNAL_STATE_EX**](../wwan/ns-wwan-_wwan_signal_state.md) contains primary information about the signal state of the device, including an array of **WWAN_SIGNAL_STATE_EXT** structures that contain signal state information specific to 5G.

For more info about 5G data class support, see [MB 5G data class support](https://docs.microsoft.com/windows-hardware/drivers/network/mb-5g-data-class-support).

## -struct-fields

### -field RSRP

The reference signal received power (RSRP), that ranges from -156 to -31, in units of 1 dBm. Use **WWAN_RSRP_UNKNOWN** when this information is not available. The following table shows how to map the range to the RSRP member.

| Reported value | Measured quantity value (L3 SS_RSRP) | Measured quantity value (L1 SS-RSRP and CSI-RSRP) | Unit |
| --- | --- | --- | --- |
| RSRP_0 | SS-RSRP<-156 | Not valid | dBm |
| RSRP_1 | -156≤ SS-RSRP<-55 | Not valid | dBm |
| RSRP_2 | -155≤ SS-RSRP<-54 | Not valid | dBm |
| RSRP_3 | -154≤ SS-RSRP<-153 | Not valid | dBm |
| RSRP_4 | -153≤ SS-RSRP<-152 | Not valid | dBm |
| RSRP_5 | -152≤ SS-RSRP<-151 | Not valid | dBm |
| ... | ... | ... | ... |
| RSRP_16 | -141≤ SS-RSRP<-140 | Not valid | dBm |
| RSRP_17 | -140≤ SS-RSRP<-139 | RSRP<-139	dBm
| RSRP_18 | -139≤ SS-RSRP<-138 | -139≤ RSRP<-138	dBm
| ... | ... | ... | ... |
| RSRP_111 | -46≤ SS-RSRP<-45 | -46≤ RSRP<-45 | dBm |
| RSRP_112 | -45≤ SS-RSRP<-44 | -45≤ RSRP | dBm |
| RSRP_113 | -44≤ SS-RSRP<-43 | Not valid | dBm |
| RSRP_114 | -43≤ SS-RSRP<-42 | Not valid | dBm |
| RSRP_115 | -42≤ SS-RSRP<-41 | Not valid | dBm |
| RSRP_116 | -41≤ SS-RSRP<-40 | Not valid | dBm |
| RSRP_117 | -40≤ SS-RSRP<-39 | Not valid | dBm |
| RSRP_118 | -39≤ SS-RSRP<-38 | Not valid | dBm |
| RSRP_119 | -38≤ SS-RSRP<-37 | Not valid | dBm |
| RSRP_120 | -37≤ SS-RSRP<-36 | Not valid | dBm |
| RSRP_121 | -36≤ SS-RSRP<-35 | Not valid | dBm |
| RSRP_122 | -35≤ SS-RSRP<-34 | Not valid | dBm |
| RSRP_123 | -34≤ SS-RSRP<-33 | Not valid | dBm |
| RSRP_124 | -33≤ SS-RSRP<-32 | Not valid | dBm |
| RSRP_125 | -32≤ SS-RSRP<-31 | Not valid | dBm |
| RSRP_126 | -31≤ SS-RSRP | Not valid | dBm |
| RSRP_127 | Infinity | Not valid | dBm |

This member is valid only if the **DataClass** member is set to **WWAN_DATA_CLASS_LTE** or **WWAN_DATA_CLASS_5G_NSA/SA**. Otherwise, use **WWAN_RSRP_UNKNOWN**.

### -field RSRPThreshold 

The current threshold, in threshold units (1 dBm), at which the miniport driver has been set (or the default threshold, if one has not been set), where the miniport driver provides updates about the signal state. Specify **WWAN_RSRP_DISABLE** to indicate that the driver does not implement threshold-based reporting. The miniport driver should populate this member with the threshold units in response to an earlier request from the MB service for **WWAN_RSRP_DEFAULT**.

This member is valid only if the **DataClass** member is set to **WWAN_DATA_CLASS_LTE** or **WWAN_DATA_CLASS_5G_NSA/SA**. Otherwise, use **WWAN_RSRP_DISABLE**.

### -field SNR

The signal-to-noise (SNR) ratio, ranging from -23 to 40, in units of 0.5 dB. Use **WWAN_SNR_UNKNOWN** when this information is not available. The following table shows how to map the range to the SNR member.

| Reported value | Measured quantity value | Unit |
| --- | --- | --- |
| SNR_0 | SNR<-23 | dB |
| SNR_1 | -23≤ SNR<-22.5 | dB |
| SNR_2 | -22.5≤ SNR<-22 | dB |
| SNR_3 | -22≤ SNR<-21.5 | dB |
| SNR_4 | -21.5≤ SNR<-21 | dB |
| ... | ... | ... |
| SNR_123 | 38≤ SNR<38.5 | dB |
| SNR_124 | 38.5≤ SNR<39 | dB |
| SNR_125 | 39≤ SNR<39.5 | dB |
| SNR_126 | 39.5≤ SNR<40 | dB |
| SNR_127 | 40≤ SNR | dB |

This member is valid only if the **DataClass** member is set to **WWAN_DATA_CLASS_LTE** or **WWAN_DATA_CLASS_5G_NSA/SA**. Otherwise, use **WWAN_SNR_UNKNOWN**.

### -field SNRThreshold

The current threshold, in threshold units (1 dBm), at which the miniport driver has been set (or the default threshold, if one has not been set), where the miniport driver provides updates about the signal state. Specify **WWAN_SNR_DISABLE** to indicate that the driver does not implement threshold-based reporting. The miniport driver should populate this member with the threshold units in response to an earlier request from the MB service for **WWAN_SNR_DEFAULT**.

This member is valid only if the **DataClass** member is set to **WWAN_DATA_CLASS_LTE** or **WWAN_DATA_CLASS_5G_NSA/SA**. Otherwise, use **WWAN_SNR_DISABLE**.

### -field DataClass

Indicates the data class for which the parameters are valid. Only if either **WWAN_DATA_CLASS_LTE** or **WWAN_DATA_CLASS_5G_NSA/SA** is set, then the **RSRP**, **RSRPThreshold**, **SNR**, and **SNRThreshold** members are valid.

## -see-also

 
[**WWAN_SIGNAL_STATE**](../wwan/ns-wwan-_wwan_signal_state.md)

