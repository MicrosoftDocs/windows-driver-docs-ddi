---
UID: NS:ucmtcpciportcontroller._UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION
title: "_UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION"
author: windows-driver-content
description: Contains identification information and USB specification version information (in BCD format) about the port controller.
old-location: buses\ucmtcpci_port_controller_identification.htm
old-project: usbref
ms.assetid: fad8ca8b-1854-4a71-a0f2-60c211ece022
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.ucmtcpci_port_controller_identification, UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION, ucmtcpciportcontroller/PUCMTCPCI_PORT_CONTROLLER_IDENTIFICATION, UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION structure [Buses], PUCMTCPCI_PORT_CONTROLLER_IDENTIFICATION structure pointer [Buses], _UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION, *PUCMTCPCI_PORT_CONTROLLER_IDENTIFICATION, ucmtcpciportcontroller/UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION, PUCMTCPCI_PORT_CONTROLLER_IDENTIFICATION
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ucmtcpciportcontroller.h
apiname:
-	UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION
product: Windows
targetos: Windows
req.typenames: "*PUCMTCPCI_PORT_CONTROLLER_IDENTIFICATION, UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION"
req.product: Windows 10 or later.
---

# _UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION structure


## -description


Contains identification information and USB specification version information (in BCD format) about the port controller.
             This client driver must specify that information in the call to <a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate.md">UcmTcpciPortControllerCreate</a> during initialization. 
                 Call <a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpci_port_controller_identification_init.md">UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION_INIT</a> to initialize this structure.
             


## -syntax


````
typedef struct _UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION {
  ULONG  Size;
  UINT16 VendorId;
  UINT16 ProductId;
  UINT16 DeviceId;
  UINT16 TypeCRevisionInBcd;
  UINT16 PDRevisionAndVersionInBcd;
  UINT16 PDInterfaceRevisionAndVersionInBcd;
} UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION, *PUCMTCPCI_PORT_CONTROLLER_IDENTIFICATION;
````


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

<a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate.md">UcmTcpciPortControllerCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

