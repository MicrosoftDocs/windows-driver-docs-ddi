---
UID: NF:nfccx.NfcCxSetRfDiscoveryConfig
title: NfcCxSetRfDiscoveryConfig function (nfccx.h)
description: Called by the client driver to configure the RF discovery parameters.
old-location: nfpdrivers\_nfccxsetrfdiscoveryconfig.htm
tech.root: nfpdrivers
ms.date: 02/15/2018
keywords: ["NfcCxSetRfDiscoveryConfig function"]
ms.keywords: NfcCxSetRfDiscoveryConfig, NfcCxSetRfDiscoveryConfig method [Near-Field Proximity Drivers], nfccx/NfcCxSetRfDiscoveryConfig, nfpdrivers._nfccxsetrfdiscoveryconfig
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
req.lib: Nfccxstub.lib
req.dll: NfcCx.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - NfcCxSetRfDiscoveryConfig
 - nfccx/NfcCxSetRfDiscoveryConfig
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NfcCx.dll
api_name:
 - NfcCxSetRfDiscoveryConfig
---

# NfcCxSetRfDiscoveryConfig function


## -description

Called by the client driver to configure the RF discovery parameters.

## -parameters

### -param Device

A handle to a framework device object.

### -param Config

A pointer to an <a href="/windows-hardware/drivers/ddi/nfccx/ns-nfccx-_nfc_cx_rf_discovery_config">NFC_CX_RF_DISCOVERY_CONFIG</a> structure.

## -returns

If the operation succeeds, the function returns STATUS_SUCCESS.

## -see-also

<a href="/windows-hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="/windows-hardware/drivers/nfc/">Near field communication (NFC) design guide</a>
