---
UID: NE:nfccx._NFC_CX_TRANSPORT_TYPE
title: _NFC_CX_TRANSPORT_TYPE
author: windows-driver-content
description: The NFC_CX_TRANSPORT_TYPE enumeration specifies transport types.
old-location: nfpdrivers\nfc_cx_transport_type.htm
old-project: nfpdrivers
ms.assetid: CC8BEC9A-87F6-4C50-A8FA-ED2A2A5D2934
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: _NFC_CX_TRANSPORT_TYPE, *PNFC_CX_TRANSPORT_TYPE, NFC_CX_TRANSPORT_TYPE
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
req.alt-api: NFC_CX_TRANSPORT_TYPE, *PNFC_CX_TRANSPORT_TYPE
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
req.typenames: *PNFC_CX_TRANSPORT_TYPE, NFC_CX_TRANSPORT_TYPE
---

# _NFC_CX_TRANSPORT_TYPE enumeration



## -description
The NFC_CX_TRANSPORT_TYPE enumeration specifies transport types.



## -syntax

````
typedef enum _NFC_CX_TRANSPORT_TYPE { 
  NFC_CX_TRANSPORT_I2C     = 0x00,
  NFC_CX_TRANSPORT_SPI     = 0x01,
  NFC_CX_TRANSPORT_UART    = 0x02,
  NFC_CX_TRANSPORT_CUSTOM  = 0xFF
} NFC_CX_TRANSPORT_TYPE, *PNFC_CX_TRANSPORT_TYPE;
````


## -enum-fields

### -field NFC_CX_TRANSPORT_I2C

Specifies an Inter-Integrated Circuit (I2C) bus.


### -field NFC_CX_TRANSPORT_SPI

Specifies a Serial Peripheral Interface (SPI).


### -field NFC_CX_TRANSPORT_UART

Specifies a Universal Asynchronous Receiver/Transmitter (UART).


### -field NFC_CX_TRANSPORT_CUSTOM

Specifies a custom transport type.


## -remarks


## -see-also
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a></dt>
<dt><a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20NFC_CX_TRANSPORT_TYPE enumeration%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

