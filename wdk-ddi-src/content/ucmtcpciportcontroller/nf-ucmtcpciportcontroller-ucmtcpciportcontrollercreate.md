---
UID: NF:ucmtcpciportcontroller.UcmTcpciPortControllerCreate
title: UcmTcpciPortControllerCreate function (ucmtcpciportcontroller.h)
description: Creates a port controller object to register with UcmTcpciCx.
old-location: buses\ucmtcpciportcontrollercreate.htm
tech.root: usbref
ms.assetid: 29862d9b-c004-445b-b90b-6990e5e01966
ms.date: 05/07/2018
ms.keywords: UcmTcpciPortControllerCreate, UcmTcpciPortControllerCreate method [Buses], buses.ucmtcpciportcontrollercreate, ucmtcpciportcontroller/UcmTcpciPortControllerCreate
ms.topic: function
req.header: ucmtcpciportcontroller.h
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
-	UcmTcpciPortControllerCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# UcmTcpciPortControllerCreate function


## -description


Creates a port controller object to register with UcmTcpciCx. 


## -parameters




### -param WdfDevice

A handle to a framework device object that the client driver received in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>. 


### -param Config

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt805900">UCMTCPCI_PORT_CONTROLLER_CONFIG</a> that is initialized by calling <b>UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT</b>. This value cannot be NULL.


### -param Attributes

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that contains driver-supplied attributes for the new object. This parameter is optional and can be <b>WDF_NO_OBJECT_ATTRIBUTES</b>.


### -param PortControllerObject

A pointer to a location that receives a handle to the new port controller object. 


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
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The handle to a framework device object is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
Invalid size for the structure pointed to by <i>Config</i> or <i> Config-&gt;Capabilities</i>. Must be size of <a href="https://msdn.microsoft.com/library/windows/hardware/mt805900">UCMTCPCI_PORT_CONTROLLER_CONFIG</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/mt805870">UCMTCPCI_PORT_CONTROLLER_CAPABILITIES</a>, respectively. 

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541693">EVT_WDF_DRIVER_DEVICE_ADD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt805900">UCMTCPCI_PORT_CONTROLLER_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>
 

 

