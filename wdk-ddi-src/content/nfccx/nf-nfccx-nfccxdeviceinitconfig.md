---
UID: NF:nfccx.NfcCxDeviceInitConfig
title: NfcCxDeviceInitConfig function
author: windows-driver-content
description: Called by the client driver during its AddDevice routine to perform DeviceInit functions. During this process the following I/O callback functions are also exchanged:
old-location: nfpdrivers\_nfccxdeviceinitconfig_.htm
old-project: nfpdrivers
ms.assetid: 98047C0F-B419-4DFE-8143-BD3917650878
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: NfcCxDeviceInitConfig, NfcCxDeviceInitConfig function [Near-Field Proximity Drivers], nfccx/NfcCxDeviceInitConfig, nfpdrivers._nfccxdeviceinitconfig_
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NfcCx.dll
api_name:
-	NfcCxDeviceInitConfig
product:
- Windows
targetos: Windows
req.typenames: 
---

# NfcCxDeviceInitConfig function


## -description


Called by the client driver during its AddDevice routine to perform DeviceInit functions. During this process the following I/O callback functions are also exchanged:
<ul>
<li>
<a href="https://msdn.microsoft.com/B734439A-E345-44CC-8FD0-8E38A718A773">EvtNfcCxWriteNciPacket </a>
</li>
<li>
<a href="https://msdn.microsoft.com/45512F88-D4B8-4488-99EB-B47EE7443425">EvtNfcCxDeviceIoControl </a>
</li>
</ul>

## -parameters




### -param DeviceInit [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure. 


### -param Config [in]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/dn905540">NFC_CX_CLIENT_CONFIG</a> structure.


## -returns



If the operation succeeds, the function returns STATUS_SUCCESS.




## -see-also




<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>
 

 

