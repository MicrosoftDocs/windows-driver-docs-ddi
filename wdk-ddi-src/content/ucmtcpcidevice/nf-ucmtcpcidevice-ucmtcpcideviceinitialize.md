---
UID: NF:ucmtcpcidevice.UcmTcpciDeviceInitialize
title: UcmTcpciDeviceInitialize function
author: windows-driver-content
description: Initializes the USB Type-C Port Controller Interface framework extension (UcmTcpciCx).
old-location: buses\ucmtcpcideviceinitialize.htm
old-project: usbref
ms.assetid: f89dd322-520b-41b0-bbe2-6eab0f8a6b70
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: UcmTcpciDeviceInitialize, UcmTcpciDeviceInitialize method [Buses], buses.ucmtcpcideviceinitialize, ucmtcpcidevice/UcmTcpciDeviceInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucmtcpcidevice.h
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
req.lib: Ucmtcpcicxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ucmtcpcicxstub.lib
-	ucmtcpcicxstub.dll
api_name:
-	UcmTcpciDeviceInitialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# UcmTcpciDeviceInitialize function


## -description


Initializes the USB Type-C Port Controller Interface framework extension (UcmTcpciCx).

                


## -parameters




### -param WdfDevice

A handle to a framework device object that the client driver received in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>. 


### -param Config

A pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/mt805896">UCMTCPCI_DEVICE_CONFIG</a> structure that is initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt805848">UCMTCPCI_DEVICE_CONFIG_INIT</a>. This value cannot be NULL.


## -returns




(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.
                    

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
Invalid size for the structure pointed to by <i>Config</i>. Must be size of <a href="https://msdn.microsoft.com/library/windows/hardware/mt805896">UCMTCPCI_DEVICE_CONFIG</a>. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_STATE</b></dt>
</dl>
</td>
<td width="60%">
The Plug and Play state of the framework device object's is uninitialized. Call <a href="https://msdn.microsoft.com/library/windows/hardware/mt805841">UcmTcpciDeviceInitialize</a> within the driver's implementation of <a href="https://msdn.microsoft.com/library/windows/hardware/ff541693">EVT_WDF_DRIVER_DEVICE_ADD</a>.

</td>
</tr>
</table>
 




## -remarks



The client driver must call <b>UcmTcpciDeviceInitialize</b> within the driver's implementation of <a href="https://msdn.microsoft.com/library/windows/hardware/ff541693">EVT_WDF_DRIVER_DEVICE_ADD</a>. This method configures the framework device object and allocates resources required, registers for PnP events, and sets up I/O targets.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>
 

 

