---
UID: NF:ucmtcpciportcontroller.UcmTcpciPortControllerCreate
title: UcmTcpciPortControllerCreate function
author: windows-driver-content
description: Creates a port controller object to register with UcmTcpciCx.
old-location: buses\ucmtcpciportcontrollercreate.htm
old-project: UsbRef
ms.assetid: 29862d9b-c004-445b-b90b-6990e5e01966
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: UcmTcpciPortControllerCreate, UcmTcpciPortControllerCreate method [Buses], buses.ucmtcpciportcontrollercreate, ucmtcpciportcontroller/UcmTcpciPortControllerCreate
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ucmtcpcicxstub.lib
-	ucmtcpcicxstub.dll
apiname:
-	UcmTcpciPortControllerCreate
product: Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE
req.product: Windows 10 or later.
---

# UcmTcpciPortControllerCreate function


## -description


Creates a port controller object to register with UcmTcpciCx. 


## -syntax


````
NTSTATUS UcmTcpciPortControllerCreate(
   WDFDEVICE                        WdfDevice,
   PUCMTCPCI_PORT_CONTROLLER_CONFIG Config,
   PWDF_OBJECT_ATTRIBUTES           Attributes,
   UCMTCPCIPORTCONTROLLER*          PortControllerObject
);
````


## -parameters




### -param WdfDevice

A handle to a framework device object that the client driver received in the previous call to <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. 


### -param Config

A pointer to the <a href="..\ucmtcpciportcontroller\ns-ucmtcpciportcontroller-_ucmtcpci_port_controller_config.md">UCMTCPCI_PORT_CONTROLLER_CONFIG</a> that is initialized by calling <b>UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT</b>. This value cannot be NULL.


### -param Attributes

A pointer to a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that contains driver-supplied attributes for the new object. This parameter is optional and can be <b>WDF_NO_OBJECT_ATTRIBUTES</b>.


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
Invalid size for the structure pointed to by <i>Config</i> or <i> Config-&gt;Capabilities</i>. Must be size of <a href="..\ucmtcpciportcontroller\ns-ucmtcpciportcontroller-_ucmtcpci_port_controller_config.md">UCMTCPCI_PORT_CONTROLLER_CONFIG</a> or <a href="..\ucmtcpciportcontroller\ns-ucmtcpciportcontroller-_ucmtcpci_port_controller_capabilities.md">UCMTCPCI_PORT_CONTROLLER_CAPABILITIES</a>, respectively. 

</td>
</tr>
</table>
 




## -see-also

<a href="..\ucmtcpciportcontroller\ns-ucmtcpciportcontroller-_ucmtcpci_port_controller_config.md">UCMTCPCI_PORT_CONTROLLER_CONFIG</a>



<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EVT_WDF_DRIVER_DEVICE_ADD</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20UcmTcpciPortControllerCreate method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

