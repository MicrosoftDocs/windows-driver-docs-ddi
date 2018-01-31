---
UID: NE:nfccx._NFC_CX_POLL_MODE_CONFIG
title: "_NFC_CX_POLL_MODE_CONFIG"
author: windows-driver-content
description: The NFC_CX_POLL_MODE_CONFIG enumeration specifies poll mode.
old-location: nfpdrivers\nfc_cx_poll_mode_config.htm
old-project: nfpdrivers
ms.assetid: A073D570-DF55-424E-8E86-49DE6A31E6FB
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: NFC_CX_POLL_MODE_CONFIG, nfccx/NFC_CX_POLL_MODE_CONFIG, nfccx/NFC_CX_POLL_NFC_F_212, NFC_CX_POLL_NFC_F_424, nfccx/NFC_CX_POLL_NFC_F_424, nfccx/NFC_CX_POLL_NFC_ACTIVE, nfccx/NFC_CX_POLL_NFC_15693, _NFC_CX_POLL_MODE_CONFIG, nfccx/NFC_CX_POLL_NFC_B, NFC_CX_POLL_NFC_A, NFC_CX_POLL_MODE_CONFIG, *PNFC_CX_POLL_MODE_CONFIG enumeration [Near-Field Proximity Drivers], NFC_CX_POLL_NFC_15693, NFC_CX_POLL_DEFAULT, nfccx/NFC_CX_POLL_DEFAULT, NFC_CX_POLL_MODE_CONFIG, *PNFC_CX_POLL_MODE_CONFIG, nfpdrivers.nfc_cx_poll_mode_config, nfccx/NFC_CX_POLL_NFC_A, *PNFC_CX_POLL_MODE_CONFIG, NFC_CX_POLL_MODE_CONFIG enumeration [Near-Field Proximity Drivers], NFC_CX_POLL_NFC_B, NFC_CX_POLL_NFC_F_212, NFC_CX_POLL_NFC_ACTIVE, PNFC_CX_POLL_MODE_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: nfccx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: Requires same
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	nfccx.h
apiname:
-	NFC_CX_POLL_MODE_CONFIG, *PNFC_CX_POLL_MODE_CONFIG
product: Windows
targetos: Windows
req.typenames: NFC_CX_POLL_MODE_CONFIG, *PNFC_CX_POLL_MODE_CONFIG
---

# _NFC_CX_POLL_MODE_CONFIG enumeration


## -description


The NFC_CX_POLL_MODE_CONFIG enumeration specifies poll mode.


## -syntax


````
typedef enum _NFC_CX_POLL_MODE_CONFIG { 
  NFC_CX_POLL_NFC_A       = 0x00000001,
  NFC_CX_POLL_NFC_B       = 0x00000002,
  NFC_CX_POLL_NFC_F_212   = 0x00000004,
  NFC_CX_POLL_NFC_F_424   = 0x00000008,
  NFC_CX_POLL_NFC_15693   = 0x00000010,
  NFC_CX_POLL_NFC_ACTIVE  = 0x00000020,
  NFC_CX_POLL_DEFAULT     = NFC_CX_POLL_NFC_A | NFC_CX_POLL_NFC_B | NFC_CX_POLL_NFC_F_212 | NFC_CX_POLL_NFC_F_424
} NFC_CX_POLL_MODE_CONFIG, *PNFC_CX_POLL_MODE_CONFIG;
````


## -enum-fields




#### - NFC_CX_POLL_NFC_A



#### - NFC_CX_POLL_NFC_B



#### - NFC_CX_POLL_NFC_F_212

NFC-F poll mode (212 kbps)


#### - NFC_CX_POLL_NFC_F_424

NFC-F poll mode (424 kbps)


#### - NFC_CX_POLL_NFC_15693



#### - NFC_CX_POLL_NFC_ACTIVE



### -field NFC_CX_POLL_NFC_A_KOVIO



#### - NFC_CX_POLL_DEFAULT



## -see-also

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>

<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20NFC_CX_POLL_MODE_CONFIG enumeration%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

