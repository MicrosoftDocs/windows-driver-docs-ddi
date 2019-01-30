---
UID: NF:ucmtcpciportcontroller.UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT
title: UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT function (ucmtcpciportcontroller.h)
description: Initializes the UCMTCPCI_PORT_CONTROLLER_CONFIG structure.
old-location: buses\ucmtcpci_port_controller_config_init.htm
tech.root: usbref
ms.assetid: 8e9718e1-2f7c-4322-a34d-2faa45f4f97e
ms.date: 05/07/2018
ms.keywords: UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT, UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT method [Buses], buses.ucmtcpci_port_controller_config_init, ucmtcpciportcontroller/UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ucmtcpciportcontroller.h
api_name:
-	UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT function


## -description



                        Initializes the <a href="https://msdn.microsoft.com/library/windows/hardware/mt805900">UCMTCPCI_PORT_CONTROLLER_CONFIG</a> structure.
                


## -parameters




### -param Config [out]

A pointer to the driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/mt805900">UCMTCPCI_PORT_CONTROLLER_CONFIG</a> structure.


### -param Identification [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt805879">UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION</a> structure.


### -param Capabilities [in]

 A pointer to the 
                 <a href="https://msdn.microsoft.com/library/windows/hardware/mt805870">UCMTCPCI_PORT_CONTROLLER_CAPABILITIES</a> structure.


## -returns



This method does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt805844">UcmTcpciPortControllerCreate</a>
 

 

