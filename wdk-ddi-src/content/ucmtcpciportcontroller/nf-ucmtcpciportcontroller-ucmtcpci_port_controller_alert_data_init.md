---
UID: NF:ucmtcpciportcontroller.UCMTCPCI_PORT_CONTROLLER_ALERT_DATA_INIT
title: UCMTCPCI_PORT_CONTROLLER_ALERT_DATA_INIT function
author: windows-driver-content
description: Initializes the UCMTCPCI_PORT_CONTROLLER_ALERT_DATA structure.
old-location: buses\ucmtcpci_port_controller_alert_data_init.htm
old-project: usbref
ms.assetid: 7c3276cc-9194-4c18-b1d8-2795efbeb357
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UCMTCPCI_PORT_CONTROLLER_ALERT_DATA_INIT, UCMTCPCI_PORT_CONTROLLER_ALERT_DATA_INIT method [Buses], buses.ucmtcpci_port_controller_alert_data_init, ucmtcpciportcontroller/UCMTCPCI_PORT_CONTROLLER_ALERT_DATA_INIT
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ucmtcpciportcontroller.h
api_name:
-	UCMTCPCI_PORT_CONTROLLER_ALERT_DATA_INIT
product: Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE
req.product: Windows 10 or later.
---

# UCMTCPCI_PORT_CONTROLLER_ALERT_DATA_INIT function


## -description



                        Initializes the <b>UCMTCPCI_PORT_CONTROLLER_ALERT_DATA</b> structure.
                
            
        Call this function before calling <a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrolleralert.md">UcmTcpciPortControllerAlert</a>.


## -syntax


````
VOID UCMTCPCI_PORT_CONTROLLER_ALERT_DATA_INIT(
  _Out_ PUCMTCPCI_PORT_CONTROLLER_ALERT_DATA AlertData
);
````


## -parameters




### -param AlertData [out]

A pointer to the driver-allocated <b>UCMTCPCI_PORT_CONTROLLER_ALERT_DATA</b> structure.


## -returns



This method does not return a value.



