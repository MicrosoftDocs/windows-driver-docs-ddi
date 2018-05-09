---
UID: NS:nfccx._NFC_CX_CLIENT_CONFIG
title: "_NFC_CX_CLIENT_CONFIG"
author: windows-driver-content
description: The NFC_CX_CLIENT_CONFIG structure is an input parameter to NfcCxDeviceInitConfig.
old-location: nfpdrivers\nfc_cx_client_config.htm
old-project: nfpdrivers
ms.assetid: 8E005C77-4234-4B32-90F2-E4A8A7CD6305
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PNFC_CX_CLIENT_CONFIG, NFC_CX_CLIENT_CONFIG, NFC_CX_CLIENT_CONFIG structure [Near-Field Proximity Drivers], PNFC_CX_CLIENT_CONFIG, PNFC_CX_CLIENT_CONFIG structure pointer [Near-Field Proximity Drivers], _NFC_CX_CLIENT_CONFIG, nfccx/PNFC_CX_CLIENT_CONFIG, nfccx/_NFC_CX_CLIENT_CONFIG, nfpdrivers.nfc_cx_client_config"
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	nfccx.h
api_name:
-	NFC_CX_CLIENT_CONFIG
product:
- Windows
targetos: Windows
req.typenames: NFC_CX_CLIENT_CONFIG, *PNFC_CX_CLIENT_CONFIG
---

# _NFC_CX_CLIENT_CONFIG structure


## -description


The NFC_CX_CLIENT_CONFIG structure is an input parameter to <a href="https://msdn.microsoft.com/98047C0F-B419-4DFE-8143-BD3917650878">NfcCxDeviceInitConfig</a>.


## -struct-fields




### -field Size

Size of this structure in bytes.




### -field IsPowerPolicyOwner

 A <a href="https://msdn.microsoft.com/library/windows/hardware/ff552533">WDF_TRI_STATE</a>-typed enumerator. 


### -field PowerIdleTimeout

IdleTimeout value, in milliseconds. Default is 1 second.




### -field PowerIdleType

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh706247">WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE</a>-typed enumerator.




### -field BusType

 An <a href="https://msdn.microsoft.com/library/windows/hardware/dn905564">NFC_CX_TRANSPORT_TYPE</a>-typed enumerator.




### -field DriverFlags

 Combination of <a href="https://msdn.microsoft.com/library/windows/hardware/dn905542">NFC_CX_DRIVER_FLAGS</a> values.




### -field DeviceMode

 Device mode.




### -field EvtNfcCxWriteNciPacket

Pointer to an <a href="https://msdn.microsoft.com/B734439A-E345-44CC-8FD0-8E38A718A773">EvtNfcCxWriteNciPacket</a> callback.


### -field EvtNfcCxDeviceIoControl

Pointer to an <a href="https://msdn.microsoft.com/45512F88-D4B8-4488-99EB-B47EE7443425">EvtNfcCxDeviceIoControl</a> callback.


## -see-also




<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>
 

 

