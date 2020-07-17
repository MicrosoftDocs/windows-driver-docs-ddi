---
UID: NS:nfccx._NFC_CX_CLIENT_CONFIG
title: _NFC_CX_CLIENT_CONFIG (nfccx.h)
description: The NFC_CX_CLIENT_CONFIG structure is an input parameter to NfcCxDeviceInitConfig.
old-location: nfpdrivers\nfc_cx_client_config.htm
tech.root: nfpdrivers
ms.assetid: 8E005C77-4234-4B32-90F2-E4A8A7CD6305
ms.date: 02/15/2018
keywords: ["_NFC_CX_CLIENT_CONFIG structure"]
ms.keywords: "*PNFC_CX_CLIENT_CONFIG, NFC_CX_CLIENT_CONFIG, NFC_CX_CLIENT_CONFIG structure [Near-Field Proximity Drivers], PNFC_CX_CLIENT_CONFIG, PNFC_CX_CLIENT_CONFIG structure pointer [Near-Field Proximity Drivers], _NFC_CX_CLIENT_CONFIG, nfccx/PNFC_CX_CLIENT_CONFIG, nfccx/_NFC_CX_CLIENT_CONFIG, nfpdrivers.nfc_cx_client_config"
f1_keywords:
 - "nfccx/NFC_CX_CLIENT_CONFIG"
 - "NFC_CX_CLIENT_CONFIG"
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
- NFC_CX_CLIENT_CONFIG
product:
- Windows
targetos: Windows
req.typenames: NFC_CX_CLIENT_CONFIG, *PNFC_CX_CLIENT_CONFIG
---

# _NFC_CX_CLIENT_CONFIG structure


## -description


The NFC_CX_CLIENT_CONFIG structure is an input parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfccx/nf-nfccx-nfccxdeviceinitconfig">NfcCxDeviceInitConfig</a>.


## -struct-fields




### -field Size

Size of this structure in bytes.




### -field IsPowerPolicyOwner

 A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdftypes/ne-wdftypes-_wdf_tri_state">WDF_TRI_STATE</a>-typed enumerator. 


### -field PowerIdleTimeout

IdleTimeout value, in milliseconds. Default is 1 second.




### -field PowerIdleType

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_power_policy_idle_timeout_type">WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE</a>-typed enumerator.




### -field BusType

 An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfccx/ne-nfccx-_nfc_cx_transport_type">NFC_CX_TRANSPORT_TYPE</a>-typed enumerator.




### -field DriverFlags

 Combination of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfccx/ne-nfccx-_nfc_cx_driver_flags">NFC_CX_DRIVER_FLAGS</a> values.




### -field DeviceMode

 Device mode.




### -field EvtNfcCxWriteNciPacket

Pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfccx/nc-nfccx-evt_nfc_cx_write_nci_packet">EvtNfcCxWriteNciPacket</a> callback.


### -field EvtNfcCxDeviceIoControl

Pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfccx/nc-nfccx-evt_nfc_cx_device_io_control">EvtNfcCxDeviceIoControl</a> callback.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="https://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>
 

 

