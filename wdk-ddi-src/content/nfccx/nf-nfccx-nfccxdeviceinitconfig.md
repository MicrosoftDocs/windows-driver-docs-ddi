---
UID: NF:nfccx.NfcCxDeviceInitConfig
title: NfcCxDeviceInitConfig function
author: windows-driver-content
description: Called by the client driver during its AddDevice routine to perform DeviceInit functions. During this process the following I/O callback functions are also exchanged:
old-location: nfpdrivers\_nfccxdeviceinitconfig_.htm
old-project: nfpdrivers
ms.assetid: 98047C0F-B419-4DFE-8143-BD3917650878
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: nfccx/NfcCxDeviceInitConfig, nfpdrivers._nfccxdeviceinitconfig_, NfcCxDeviceInitConfig, NfcCxDeviceInitConfig function [Near-Field Proximity Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NfcCx.dll
apiname:
-	NfcCxDeviceInitConfig
product: Windows
targetos: Windows
req.typenames: NFC_CX_TRANSPORT_TYPE, *PNFC_CX_TRANSPORT_TYPE
---

# NfcCxDeviceInitConfig function


## -description


Called by the client driver during its AddDevice routine to perform DeviceInit functions. During this process the following I/O callback functions are also exchanged:
<ul>
<li>
<a href="..\nfccx\nc-nfccx-evt_nfc_cx_write_nci_packet.md">EvtNfcCxWriteNciPacket </a>
</li>
<li>
<a href="..\nfccx\nc-nfccx-evt_nfc_cx_device_io_control.md">EvtNfcCxDeviceIoControl </a>
</li>
</ul>

## -syntax


````
NTSTATUS NfcCxDeviceInitConfig (
  _Inout_  PWDFDEVICE_INIT      DeviceInit,
  _In_    PNFC_CX_CLIENT_CONFIG Config
);
````


## -parameters




### -param DeviceInit [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure. 


### -param Config [in]

A pointer to an <a href="..\nfccx\ns-nfccx-_nfc_cx_client_config.md">NFC_CX_CLIENT_CONFIG</a> structure.


## -returns



If the operation succeeds, the function returns STATUS_SUCCESS.




## -see-also

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20NfcCxDeviceInitConfig function%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

