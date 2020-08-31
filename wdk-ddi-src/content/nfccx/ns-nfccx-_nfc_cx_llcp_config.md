---
UID: NS:nfccx._NFC_CX_LLCP_CONFIG
title: _NFC_CX_LLCP_CONFIG (nfccx.h)
description: The NFC_CX_LLCP_CONFIG structure is an input parameter to NfcCxSetLlcpConfig.
old-location: nfpdrivers\nfc_cx_llcp_config.htm
tech.root: nfpdrivers
ms.assetid: 84A1F957-FAAE-4C2D-9D49-486813A26950
ms.date: 02/15/2018
keywords: ["NFC_CX_LLCP_CONFIG structure"]
ms.keywords: "*PNFC_CX_LLCP_CONFIG, NFC_CX_LLCP_CONFIG, NFC_CX_LLCP_CONFIG structure [Near-Field Proximity Drivers], PNFC_CX_LLCP_CONFIG, PNFC_CX_LLCP_CONFIG structure pointer [Near-Field Proximity Drivers], _NFC_CX_LLCP_CONFIG, nfccx/NFC_CX_LLCP_CONFIG, nfccx/PNFC_CX_LLCP_CONFIG, nfpdrivers.nfc_cx_llcp_config"
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
targetos: Windows
req.typenames: NFC_CX_LLCP_CONFIG, *PNFC_CX_LLCP_CONFIG
f1_keywords:
 - _NFC_CX_LLCP_CONFIG
 - nfccx/_NFC_CX_LLCP_CONFIG
 - PNFC_CX_LLCP_CONFIG
 - nfccx/PNFC_CX_LLCP_CONFIG
 - NFC_CX_LLCP_CONFIG
 - nfccx/NFC_CX_LLCP_CONFIG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - nfccx.h
api_name:
 - NFC_CX_LLCP_CONFIG
---

# _NFC_CX_LLCP_CONFIG structure


## -description

The NFC_CX_LLCP_CONFIG structure is an input parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfccx/nf-nfccx-nfccxsetllcpconfig">NfcCxSetLlcpConfig.</a>

## -struct-fields

### -field Size

 Size of this structure in bytes.

### -field Miu

Max information unit in bytes. Default is 1024.

### -field LinkTimeout

 LTO timeout in multiples of 10 milliseconds. Default is 100 (1 second).

### -field RecvWindowSize

The receive window size per LLCP spec. Default value is 5.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="https://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>

