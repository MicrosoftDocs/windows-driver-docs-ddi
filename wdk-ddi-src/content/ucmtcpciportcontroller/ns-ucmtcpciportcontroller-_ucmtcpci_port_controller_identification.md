---
UID: NS:ucmtcpciportcontroller._UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION
title: "_UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION" (ucmtcpciportcontroller.h)
description: Contains identification information and USB specification version information (in BCD format) about the port controller.
old-location: buses\ucmtcpci_port_controller_identification.htm
tech.root: usbref
ms.assetid: fad8ca8b-1854-4a71-a0f2-60c211ece022
ms.date: 05/07/2018
ms.keywords: "*PUCMTCPCI_PORT_CONTROLLER_IDENTIFICATION, PUCMTCPCI_PORT_CONTROLLER_IDENTIFICATION, PUCMTCPCI_PORT_CONTROLLER_IDENTIFICATION structure pointer [Buses], UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION, UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION structure [Buses], _UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION, buses.ucmtcpci_port_controller_identification, ucmtcpciportcontroller/PUCMTCPCI_PORT_CONTROLLER_IDENTIFICATION, ucmtcpciportcontroller/UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION"
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
-	UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION
product:
- Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION, *PUCMTCPCI_PORT_CONTROLLER_IDENTIFICATION
---

# _UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION structure


## -description


Contains identification information and USB specification version information (in BCD format) about the port controller.
             This client driver must specify that information in the call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt805844">UcmTcpciPortControllerCreate</a> during initialization. 
                 Call <a href="https://msdn.microsoft.com/library/windows/hardware/mt805880">UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION_INIT</a> to initialize this structure.
             


## -struct-fields




### -field Size

Size of this structure.


### -field VendorId

Specifies the vendor identifier assigned by the USB specification committee.
                     
                 


### -field ProductId


                     Specifies the product identifier. This value is assigned by the manufacturer.
                 


### -field DeviceId


                     The device ID for the USB Type-C port  controller.
                 


### -field TypeCRevisionInBcd


                     The revision ID for the USB Type-C port  controller.
                 


### -field PDRevisionAndVersionInBcd


                     
                     The revision and version for the USB Type-C port  controller that supports PD.
                 


### -field PDInterfaceRevisionAndVersionInBcd


                     
                     The interface revision and version for the USB Type-C port  controller that supports PD.
                 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt805844">UcmTcpciPortControllerCreate</a>
 

 

