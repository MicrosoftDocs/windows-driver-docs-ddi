---
UID: NF:ucmtcpcidevice.UcmTcpciDeviceInitialize
title: UcmTcpciDeviceInitialize function
author: windows-driver-content
description: Initializes the USB Type-C Port Controller Interface framework extension (UcmTcpciCx).
old-location: buses\ucmtcpcideviceinitialize.htm
old-project: usbref
ms.assetid: f89dd322-520b-41b0-bbe2-6eab0f8a6b70
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UcmTcpciDeviceInitialize, UcmTcpciDeviceInitialize method [Buses], ucmtcpcidevice/UcmTcpciDeviceInitialize, buses.ucmtcpcideviceinitialize
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ucmtcpcicxstub.lib
-	ucmtcpcicxstub.dll
apiname:
-	UcmTcpciDeviceInitialize
product: Windows
targetos: Windows
req.typenames: UCM_MANAGER_CONFIG, *PUCM_MANAGER_CONFIG
req.product: Windows 10 or later.
---

# UcmTcpciDeviceInitialize function


## -description


Initializes the USB Type-C Port Controller Interface framework extension (UcmTcpciCx).

                


## -syntax


````
NTSTATUS UcmTcpciDeviceInitialize(
   WDFDEVICE               WdfDevice,
   PUCMTCPCI_DEVICE_CONFIG Config
);
````


## -parameters




### -param WdfDevice

A handle to a framework device object that the client driver received in the previous call to <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. 


### -param Config

A pointer to a caller-supplied <a href="..\ucmtcpcidevice\ns-ucmtcpcidevice-_ucmtcpci_device_config.md">UCMTCPCI_DEVICE_CONFIG</a> structure that is initialized by calling <a href="..\ucmtcpcidevice\nf-ucmtcpcidevice-ucmtcpci_device_config_init.md">UCMTCPCI_DEVICE_CONFIG_INIT</a>. This value cannot be NULL.


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
Invalid size for the structure pointed to by <i>Config</i>. Must be size of <a href="..\ucmtcpcidevice\ns-ucmtcpcidevice-_ucmtcpci_device_config.md">UCMTCPCI_DEVICE_CONFIG</a>. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_STATE</b></dt>
</dl>
</td>
<td width="60%">
The Plug and Play state of the framework device object's is uninitialized. Call <a href="..\ucmtcpcidevice\nf-ucmtcpcidevice-ucmtcpcideviceinitialize.md">UcmTcpciDeviceInitialize</a> within the driver's implementation of <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EVT_WDF_DRIVER_DEVICE_ADD</a>.

</td>
</tr>
</table> 



## -remarks


The client driver must call <b>UcmTcpciDeviceInitialize</b> within the driver's implementation of <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EVT_WDF_DRIVER_DEVICE_ADD</a>. This method configures the framework device object and allocates resources required, registers for PnP events, and sets up I/O targets.



## -see-also

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UcmTcpciDeviceInitialize method%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

