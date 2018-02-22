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
ms.keywords: PNFC_CX_CLIENT_CONFIG, NFC_CX_CLIENT_CONFIG, NFC_CX_CLIENT_CONFIG structure [Near-Field Proximity Drivers], nfccx/PNFC_CX_CLIENT_CONFIG, _NFC_CX_CLIENT_CONFIG, *PNFC_CX_CLIENT_CONFIG, nfpdrivers.nfc_cx_client_config, PNFC_CX_CLIENT_CONFIG structure pointer [Near-Field Proximity Drivers], nfccx/_NFC_CX_CLIENT_CONFIG
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	nfccx.h
apiname:
-	NFC_CX_CLIENT_CONFIG
product: Windows
targetos: Windows
req.typenames: NFC_CX_CLIENT_CONFIG, *PNFC_CX_CLIENT_CONFIG
---

# _NFC_CX_CLIENT_CONFIG structure


## -description


The NFC_CX_CLIENT_CONFIG structure is an input parameter to <a href="..\nfccx\nf-nfccx-nfccxdeviceinitconfig.md">NfcCxDeviceInitConfig</a>.


## -syntax


````
typedef struct _NFC_CX_CLIENT_CONFIG {
  ULONG                              Size;
  WDF_TRI_STATE                      IsPowerPolicyOwner;
  ULONG                              PowerIdleTimeout;
  WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE PowerIdleType;
  NFC_CX_TRANSPORT_TYPE              BusType;
  ULONG                              DriverFlags;
  NFC_CX_DEVICE_MODE                 DeviceMode;
  PFN_NFC_CX_WRITE_NCI_PACKET        EvtNfcCxWriteNciPacket;
  PFN_NFC_CX_DEVICE_IO_CONTROL       EvtNfcCxDeviceIoControl;
} NFC_CX_CLIENT_CONFIG, *PNFC_CX_CLIENT_CONFIG;
````


## -struct-fields




### -field Size

Size of this structure in bytes.




### -field IsPowerPolicyOwner

 A <a href="..\wdftypes\ne-wdftypes-_wdf_tri_state.md">WDF_TRI_STATE</a>-typed enumerator. 


### -field PowerIdleTimeout

IdleTimeout value, in milliseconds. Default is 1 second.




### -field PowerIdleType

A <a href="..\wdfdevice\ne-wdfdevice-_wdf_power_policy_idle_timeout_type.md">WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE</a>-typed enumerator.




### -field BusType

 An <a href="..\nfccx\ne-nfccx-_nfc_cx_transport_type.md">NFC_CX_TRANSPORT_TYPE</a>-typed enumerator.




### -field DriverFlags

 Combination of <a href="..\nfccx\ne-nfccx-_nfc_cx_driver_flags.md">NFC_CX_DRIVER_FLAGS</a> values.




### -field DeviceMode

 Device mode.




### -field EvtNfcCxWriteNciPacket

Pointer to an <a href="..\nfccx\nc-nfccx-evt_nfc_cx_write_nci_packet.md">EvtNfcCxWriteNciPacket</a> callback.


### -field EvtNfcCxDeviceIoControl

Pointer to an <a href="..\nfccx\nc-nfccx-evt_nfc_cx_device_io_control.md">EvtNfcCxDeviceIoControl</a> callback.


## -see-also

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20NFC_CX_CLIENT_CONFIG structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

