---
UID: NS:nfccx._NFC_CX_RF_DISCOVERY_CONFIG
title: _NFC_CX_RF_DISCOVERY_CONFIG
author: windows-driver-content
description: The NFC_CX_RF_DISCOVERY_CONFIG structure contains RF discovery configuration settings. Discovery configuration should be completed during initialization after calling NfcDxDeviceInitialize, otherwise an error is returned.
old-location: nfpdrivers\nfc_cx_rf_discovery_config.htm
old-project: nfpdrivers
ms.assetid: 4EF45183-335C-40FC-8693-BF3D17B18DF2
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: _NFC_CX_RF_DISCOVERY_CONFIG, NFC_CX_RF_DISCOVERY_CONFIG, *PNFC_CX_RF_DISCOVERY_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: nfccx.h
req.include-header: Ncidef.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NFC_CX_RF_DISCOVERY_CONFIG
req.alt-loc: nfccx.h
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
req.typenames: NFC_CX_RF_DISCOVERY_CONFIG, *PNFC_CX_RF_DISCOVERY_CONFIG
---

# _NFC_CX_RF_DISCOVERY_CONFIG structure



## -description
The <b>NFC_CX_RF_DISCOVERY_CONFIG</b> structure contains RF discovery configuration settings. Discovery configuration should be completed during initialization after calling <a href="..\nfccx\nf-nfccx-nfccxdevicedeinitialize.md">NfcDxDeviceInitialize</a>, otherwise an error is returned.



## -syntax

````
typedef struct _NFC_CX_RF_DISCOVERY_CONFIG {
  ULONG  Size;
  USHORT TotalDuration;
  ULONG  PollConfig;
  UCHAR  NfcIPMode;
  UCHAR  NfcIPTgtMode;
  UCHAR  NfcCEMode;
  UCHAR  BailoutConfig;
} NFC_CX_RF_DISCOVERY_CONFIG, *PNFC_CX_RF_DISCOVERY_CONFIG;
````


## -struct-fields

### -field Size

 Size of this structure in bytes.


### -field TotalDuration

 Total duration of the single discovery period in milliseconds. Default is 300 milliseconds.

This member corresponds to TOTAL_DURATION specified in the NCI specification. Values can be between 0 to 0xFFFF.  Use an appropriate value that factors into account both the discovery latency as well as power consumption.


### -field PollConfig

Combination of <a href="..\nfccx\ne-nfccx-_nfc_cx_poll_mode_config.md">NFC_CX_POLL_MODE_CONFIG</a> values. 

This member enables configuration of poll mode settings. The default enables polling for passive poll NFC-A, passive poll NFC-B, and passive poll NFC-F (212 and 424k). Its recommended that NFC clients configure additional active modes if they are supported.


### -field NfcIPMode

 Combination of <a href="..\nfccx\ne-nfccx-_nfc_cx_nfcip_mode_config.md">NFC_CX_NFCIP_MODE_CONFIG</a> values.

This member enables configuration of NFC-IP initiator mode settings. The value corresponds to combination of NFC_CX_NFCIP_MODE_CONFIG enum. The default enables polling for passive poll NFC-A and passive poll NFC-F (212 and 424k) phases.


### -field NfcIPTgtMode

 Combination of <a href="..\nfccx\ne-nfccx-_nfc_cx_nfcip_tgt_mode_config.md">NFC_CX_NFCIP_TGT_MODE_CONFIG</a> values.

This member enables configuration of NFC-IP target mode settings. The default enables passive listen NFC-A and passive listen NFC-F phases.


### -field NfcCEMode

 Combination of <a href="..\nfccx\ne-nfccx-_nfc_cx_ce_mode_config.md">NFC_CX_CE_MODE_CONFIG</a> values. 

This member enables configuration of NFC-CE mode settings. The default enables passive listen NFC-A, passive listen NFC-B, and passive listen NFC-F phases.


### -field BailoutConfig

Combination of <a href="..\nfccx\ne-nfccx-_nfc_cx_poll_bailout_config.md">NFC_CX_POLL_BAILOUT_CONFIG</a> values. Default is disabled.

This member enables configuration of PA_BAIL_OUT and PB_BAIL_OUT as described in the NCI specification. 


## -remarks


## -see-also
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a></dt>
<dt><a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20NFC_CX_RF_DISCOVERY_CONFIG structure%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

