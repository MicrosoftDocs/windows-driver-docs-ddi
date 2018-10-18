---
UID: NS:ucmtcpciportcontroller._UCMTCPCI_PORT_CONTROLLER_CAPABILITIES
title: "_UCMTCPCI_PORT_CONTROLLER_CAPABILITIES"
author: windows-driver-content
description: Contains information about the capabilities of the port controller.
old-location: buses\ucmtcpci_port_controller_capabilities.htm
tech.root: usbref
ms.assetid: 829bb05b-5e2d-4aba-ab34-127812235f46
ms.date: 5/7/2018
ms.keywords: "*PUCMTCPCI_PORT_CONTROLLER_CAPABILITIES, PUCMTCPCI_PORT_CONTROLLER_CAPABILITIES, PUCMTCPCI_PORT_CONTROLLER_CAPABILITIES structure pointer [Buses], UCMTCPCI_PORT_CONTROLLER_CAPABILITIES, UCMTCPCI_PORT_CONTROLLER_CAPABILITIES structure [Buses], _UCMTCPCI_PORT_CONTROLLER_CAPABILITIES, buses.ucmtcpci_port_controller_capabilities, ucmtcpciportcontroller/PUCMTCPCI_PORT_CONTROLLER_CAPABILITIES, ucmtcpciportcontroller/UCMTCPCI_PORT_CONTROLLER_CAPABILITIES"
ms.topic: struct
req.header: ucmtcpciportcontroller.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ucmtcpciportcontroller.h
api_name:
-	UCMTCPCI_PORT_CONTROLLER_CAPABILITIES
product:
- Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_CAPABILITIES, *PUCMTCPCI_PORT_CONTROLLER_CAPABILITIES
---

# _UCMTCPCI_PORT_CONTROLLER_CAPABILITIES structure


## -description


Contains information about the capabilities of the port controller.
             This client driver must specify that information in the call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt805844">UcmTcpciPortControllerCreate</a> during initialization. 
                 Call <a href="https://msdn.microsoft.com/library/windows/hardware/mt805871">UCMTCPCI_PORT_CONTROLLER_CAPABILITIES_INIT</a> to initialize this structure.
             


## -struct-fields




### -field Size


                     The size of this structure.
                 


### -field IsPowerDeliveryCapable


                     Indicates whether the port controller supports <a href="http://go.microsoft.com/fwlink/p/?LinkID=623310">USB Power Delivery</a>.


### -field DeviceCapabilities1


                     A 
                 <b>UCMTCPCI_PORT_CONTROLLER_DEVICE_CAPABILITIES_1</b> structure that describes the  DEVICE_CAPABILITIES_1 Register as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.


### -field DeviceCapabilities2


                     A 
                 <b>UCMTCPCI_PORT_CONTROLLER_DEVICE_CAPABILITIES_2</b> structure that describes the  DEVICE_CAPABILITIES_2 Register as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.


### -field StandardInputCapabilities


                     A 
                 <b>UCMTCPCI_PORT_CONTROLLER_STANDARD_INPUT_CAPABILITIES</b> structure that describes the  STANDARD_INPUT_CAPABILITIES Register as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.


### -field StandardOutputCapabilities


                     A 
                 <b>UCMTCPCI_PORT_CONTROLLER_STANDARD_OUTPUT_CAPABILITIES</b> structure that describes the  STANDARD_OUTPUT_CAPABILITIES Register as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt805871">UCMTCPCI_PORT_CONTROLLER_CAPABILITIES_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt805844">UcmTcpciPortControllerCreate</a>
 

 

