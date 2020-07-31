---
UID: NS:nfccx._NFC_CX_RF_DISCOVERY_CONFIG
title: _NFC_CX_RF_DISCOVERY_CONFIG (nfccx.h)
description: The NFC_CX_RF_DISCOVERY_CONFIG structure contains RF discovery configuration settings. Discovery configuration should be completed during initialization after calling NfcDxDeviceInitialize, otherwise an error is returned.
old-location: nfpdrivers\nfc_cx_rf_discovery_config.htm
tech.root: nfpdrivers
ms.assetid: 4EF45183-335C-40FC-8693-BF3D17B18DF2
ms.date: 02/15/2018
keywords: ["_NFC_CX_RF_DISCOVERY_CONFIG structure"]
ms.keywords: "*PNFC_CX_RF_DISCOVERY_CONFIG, NFC_CX_RF_DISCOVERY_CONFIG, NFC_CX_RF_DISCOVERY_CONFIG structure [Near-Field Proximity Drivers], PNFC_CX_RF_DISCOVERY_CONFIG, PNFC_CX_RF_DISCOVERY_CONFIG structure pointer [Near-Field Proximity Drivers], _NFC_CX_RF_DISCOVERY_CONFIG, nfccx/NFC_CX_RF_DISCOVERY_CONFIG, nfccx/PNFC_CX_RF_DISCOVERY_CONFIG, nfpdrivers.nfc_cx_rf_discovery_config"
f1_keywords:
 - "nfccx/NFC_CX_RF_DISCOVERY_CONFIG"
 - "NFC_CX_RF_DISCOVERY_CONFIG"
req.header: nfccx.h
req.include-header: Ncidef.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
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
- HeaderDef
api_location:
- nfccx.h
api_name:
- NFC_CX_RF_DISCOVERY_CONFIG
targetos: Windows
req.typenames: NFC_CX_RF_DISCOVERY_CONFIG, *PNFC_CX_RF_DISCOVERY_CONFIG
---

# _NFC_CX_RF_DISCOVERY_CONFIG structure


## -description


The <b>NFC_CX_RF_DISCOVERY_CONFIG</b> structure contains RF discovery configuration settings. Discovery configuration should be completed during initialization after calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfccx/nf-nfccx-nfccxdevicedeinitialize">NfcDxDeviceInitialize</a>, otherwise an error is returned.


## -struct-fields




### -field Size

 Size of this structure in bytes.


### -field TotalDuration

 Total duration of the single discovery period in milliseconds. Default is 300 milliseconds.

This member corresponds to TOTAL_DURATION specified in the NCI specification. Values can be between 0 to 0xFFFF.  Use an appropriate value that factors into account both the discovery latency as well as power consumption.


### -field PollConfig

Combination of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfccx/ne-nfccx-_nfc_cx_poll_mode_config">NFC_CX_POLL_MODE_CONFIG</a> values. 

This member enables configuration of poll mode settings. The default enables polling for passive poll NFC-A, passive poll NFC-B, and passive poll NFC-F (212 and 424k). Its recommended that NFC clients configure additional active modes if they are supported.


### -field NfcIPMode

 Combination of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfccx/ne-nfccx-_nfc_cx_nfcip_mode_config">NFC_CX_NFCIP_MODE_CONFIG</a> values.

This member enables configuration of NFC-IP initiator mode settings. The value corresponds to combination of NFC_CX_NFCIP_MODE_CONFIG enum. The default enables polling for passive poll NFC-A and passive poll NFC-F (212 and 424k) phases.


### -field NfcIPTgtMode

 Combination of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfccx/ne-nfccx-_nfc_cx_nfcip_tgt_mode_config">NFC_CX_NFCIP_TGT_MODE_CONFIG</a> values.

This member enables configuration of NFC-IP target mode settings. The default enables passive listen NFC-A and passive listen NFC-F phases.


### -field NfcCEMode

 Combination of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfccx/ne-nfccx-_nfc_cx_ce_mode_config">NFC_CX_CE_MODE_CONFIG</a> values. 

This member enables configuration of NFC-CE mode settings. The default enables passive listen NFC-A, passive listen NFC-B, and passive listen NFC-F phases.


### -field BailoutConfig

Combination of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfccx/ne-nfccx-_nfc_cx_poll_bailout_config">NFC_CX_POLL_BAILOUT_CONFIG</a> values. Default is disabled.

This member enables configuration of PA_BAIL_OUT and PB_BAIL_OUT as described in the NCI specification. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="https://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>
 

 

