---
UID: NS:dxva._DXVA_EncryptProtocolHeader
title: _DXVA_EncryptProtocolHeader (dxva.h)
description: The DXVA_EncryptProtocolHeader structure is sent by the host decoder to the accelerator to indicate use of an encryption protocol.
old-location: display\dxva_encryptprotocolheader.htm
tech.root: display
ms.assetid: 924da940-f609-4302-b454-87243200808e
ms.date: 05/10/2018
ms.keywords: "*LPDXVA_EncryptProtocolHeader, DXVA_EncryptProtocolHeader, DXVA_EncryptProtocolHeader structure [Display Devices], LPDXVA_EncryptProtocolHeader, LPDXVA_EncryptProtocolHeader structure pointer [Display Devices], _DXVA_EncryptProtocolHeader, display.dxva_encryptprotocolheader, dxva/DXVA_EncryptProtocolHeader, dxva/LPDXVA_EncryptProtocolHeader, dxvaref_19bd4a66-c03f-44c3-98b6-875da968fa50.xml"
f1_keywords:
 - "dxva/DXVA_EncryptProtocolHeader"
req.header: dxva.h
req.include-header: Dxva.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- dxva.h
api_name:
- DXVA_EncryptProtocolHeader
product:
- Windows
targetos: Windows
req.typenames: DXVA_EncryptProtocolHeader, *LPDXVA_EncryptProtocolHeader
---

# _DXVA_EncryptProtocolHeader structure


## -description


The DXVA_EncryptProtocolHeader structure is sent by the host decoder to the accelerator to indicate use of an encryption protocol.


## -struct-fields




### -field dwFunction

Indicates whether encryption is being used and the operation to which encryption applies. The 24 most significant bits of <b>dwFunction</b> indicate that an encryption protocol is being used. These bits must be 0xFFFF00 when sent by the host software decoder, and 0xFFFF08 when sent by the accelerator. The 8 least significant bits of <b>dwFunction</b> contain a <a href="https://docs.microsoft.com/windows-hardware/drivers/display/bdxva-func-variable">bDXVA_Func</a> variable that indicates the operation to which the encryption protocol applies. Currently, the only relevant defined value of <i>bDXVA_Func</i> for use in these bits is 1, which indicates that the encryption protocol applies to compressed picture decoding.

There are only two possible values for <b>dwFunction</b> in this structure: 0xFFFF0001 when sent by a host software decoder, and 0xFFFF0801 when sent by the hardware accelerator.


### -field ReservedBits

Reserved bits used for packing and alignment. This must be zero.


### -field guidEncryptProtocol

Contains the GUID associated with the encryption protocol.


## -remarks



The encryption protocol in use is externally defined and operates as described in <a href="https://docs.microsoft.com/windows-hardware/drivers/display/encryption-support">Encryption Support</a>.



