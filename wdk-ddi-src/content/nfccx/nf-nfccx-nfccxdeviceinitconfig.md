---
UID: NF:nfccx.NfcCxDeviceInitConfig
title: NfcCxDeviceInitConfig function (nfccx.h)
description: Called by the client driver during its AddDevice routine to perform DeviceInit functions. During this process the following I/O callback functions are also exchanged.
old-location: nfpdrivers\_nfccxdeviceinitconfig_.htm
tech.root: nfpdrivers
ms.assetid: 98047C0F-B419-4DFE-8143-BD3917650878
ms.date: 02/15/2018
keywords: ["NfcCxDeviceInitConfig function"]
ms.keywords: NfcCxDeviceInitConfig, NfcCxDeviceInitConfig function [Near-Field Proximity Drivers], nfccx/NfcCxDeviceInitConfig, nfpdrivers._nfccxdeviceinitconfig_
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
 - NfcCxDeviceInitConfig
 - nfccx/NfcCxDeviceInitConfig
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NfcCx.dll
api_name:
 - NfcCxDeviceInitConfig
---

# NfcCxDeviceInitConfig function


## -description

Called by the client driver during its AddDevice routine to perform DeviceInit functions. During this process the following I/O callback functions are also exchanged:
<ul>
<li>
<a href="/windows-hardware/drivers/ddi/nfccx/nc-nfccx-evt_nfc_cx_write_nci_packet">EvtNfcCxWriteNciPacket </a>
</li>
<li>
<a href="/windows-hardware/drivers/ddi/nfccx/nc-nfccx-evt_nfc_cx_device_io_control">EvtNfcCxDeviceIoControl </a>
</li>
</ul>

## -parameters

### -param DeviceInit 

[in, out]
A pointer to a <a href="/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure.

### -param Config 

[in]
A pointer to an <a href="/windows-hardware/drivers/ddi/nfccx/ns-nfccx-_nfc_cx_client_config">NFC_CX_CLIENT_CONFIG</a> structure.

## -returns

If the operation succeeds, the function returns STATUS_SUCCESS.

## -see-also

<a href="/windows-hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="/windows-hardware/drivers/nfc/">Near field communication (NFC) design guide</a>