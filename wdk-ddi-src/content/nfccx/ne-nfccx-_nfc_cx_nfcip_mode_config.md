---
UID: NE:nfccx._NFC_CX_NFCIP_MODE_CONFIG
title: _NFC_CX_NFCIP_MODE_CONFIG
author: windows-driver-content
description: The NFC_CX_NFCIP_MODE_CONFIG enumeration specifies the NFC-IP initiator mode.
old-location: nfpdrivers\nfc_cx_nfcip_mode_config.htm
old-project: nfpdrivers
ms.assetid: B922FF18-8840-4BBB-8B32-BEF7B6DE4731
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: _NFC_CX_NFCIP_MODE_CONFIG, NFC_CX_NFCIP_MODE_CONFIG, *PNFC_CX_NFCIP_MODE_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: nfccx.h
req.include-header: Ncidef.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NFC_CX_NFCIP_MODE_CONFIG, *PNFC_CX_NFCIP_MODE_CONFIG
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
req.irql: Requires same
req.typenames: NFC_CX_NFCIP_MODE_CONFIG, *PNFC_CX_NFCIP_MODE_CONFIG
---

# _NFC_CX_NFCIP_MODE_CONFIG enumeration



## -description
The NFC_CX_NFCIP_MODE_CONFIG enumeration specifies the NFC-IP initiator mode.



## -syntax

````
typedef enum _NFC_CX_NFCIP_MODE_CONFIG { 
  NFC_CX_NFCIP_NFC_A             = 0x01,
  NFC_CX_NFCIP_NFC_F_212         = 0x02,
  NFC_CX_NFCIP_NFC_F_424         = 0x04,
  NFC_CX_NFCIP_NFC_ACTIVE        = 0x08,
  NFC_CX_NFCIP_NFC_ACTIVE_A      = 0x10,
  NFC_CX_NFCIP_NFC_ACTIVE_F_212  = 0x20,
  NFC_CX_NFCIP_NFC_ACTIVE_F_424  = 0x40,
  NFC_CX_NFCIP_DEFAULT           = NFC_CX_NFCIP_NFC_A | NFC_CX_NFCIP_NFC_F_212 | NFC_CX_NFCIP_NFC_F_424
} NFC_CX_NFCIP_MODE_CONFIG, *PNFC_CX_NFCIP_MODE_CONFIG;
````


## -enum-fields

### -field NFC_CX_NFCIP_NFC_A


### -field NFC_CX_NFCIP_NFC_F_212


### -field NFC_CX_NFCIP_NFC_F_424


### -field NFC_CX_NFCIP_NFC_ACTIVE


### -field NFC_CX_NFCIP_NFC_ACTIVE_A


### -field NFC_CX_NFCIP_NFC_ACTIVE_F_212


### -field NFC_CX_NFCIP_NFC_ACTIVE_F_424


### -field NFC_CX_NFCIP_DEFAULT


## -remarks


## -see-also
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a></dt>
<dt><a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20NFC_CX_NFCIP_MODE_CONFIG enumeration%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

