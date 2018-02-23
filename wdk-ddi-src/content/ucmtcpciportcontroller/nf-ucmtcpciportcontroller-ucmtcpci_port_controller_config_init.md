---
UID: NF:ucmtcpciportcontroller.UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT
title: UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT function
author: windows-driver-content
description: Initializes the UCMTCPCI_PORT_CONTROLLER_CONFIG structure.
old-location: buses\ucmtcpci_port_controller_config_init.htm
old-project: UsbRef
ms.assetid: 8e9718e1-2f7c-4322-a34d-2faa45f4f97e
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT, UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT method [Buses], buses.ucmtcpci_port_controller_config_init, ucmtcpciportcontroller/UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ucmtcpciportcontroller.h
apiname:
-	UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE
req.product: Windows 10 or later.
---

# UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT function


## -description



                        Initializes the <a href="..\ucmtcpciportcontroller\ns-ucmtcpciportcontroller-_ucmtcpci_port_controller_config.md">UCMTCPCI_PORT_CONTROLLER_CONFIG</a> structure.
                


## -syntax


````
VOID UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT(
  _Out_ PUCMTCPCI_PORT_CONTROLLER_CONFIG         Config,
  _In_  PUCMTCPCI_PORT_CONTROLLER_IDENTIFICATION Identification,
  _In_  PUCMTCPCI_PORT_CONTROLLER_CAPABILITIES   Capabilities
);
````


## -parameters




### -param Config [out]

A pointer to the driver-allocated <a href="..\ucmtcpciportcontroller\ns-ucmtcpciportcontroller-_ucmtcpci_port_controller_config.md">UCMTCPCI_PORT_CONTROLLER_CONFIG</a> structure.


### -param Identification [in]

A pointer to the <a href="..\ucmtcpciportcontroller\ns-ucmtcpciportcontroller-_ucmtcpci_port_controller_identification.md">UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION</a> structure.


### -param Capabilities [in]

 A pointer to the 
                 <a href="..\ucmtcpciportcontroller\ns-ucmtcpciportcontroller-_ucmtcpci_port_controller_capabilities.md">UCMTCPCI_PORT_CONTROLLER_CAPABILITIES</a> structure.


## -returns



This method does not return a value.




## -see-also

<a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate.md">UcmTcpciPortControllerCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

