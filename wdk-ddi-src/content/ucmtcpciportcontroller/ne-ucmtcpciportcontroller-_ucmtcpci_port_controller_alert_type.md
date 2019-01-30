---
UID: NE:ucmtcpciportcontroller._UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE
title: "_UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE" (ucmtcpciportcontroller.h)
description: Defines generic alert values that are used to indicate the type of hardware alert received on the port controller.
old-location: buses\ucmtcpci_port_controller_alert_type.htm
tech.root: usbref
ms.assetid: 77162a25-b5aa-45d0-ac4d-6500df9782de
ms.date: 05/07/2018
ms.keywords: UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE, UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE enumeration [Buses], UcmTcpciPortControllerAlertCCStatus, UcmTcpciPortControllerAlertFault, UcmTcpciPortControllerAlertInvalid, UcmTcpciPortControllerAlertPowerStatus, UcmTcpciPortControllerAlertReceiveSOPMessageStatus, UcmTcpciPortControllerAlertReceivedHardReset, UcmTcpciPortControllerAlertRxBufferOverflow, UcmTcpciPortControllerAlertTransmitSOPMessageDiscarded, UcmTcpciPortControllerAlertTransmitSOPMessageFailed, UcmTcpciPortControllerAlertTransmitSOPMessageSuccessful, UcmTcpciPortControllerAlertVbusSinkDisconnectDetected, UcmTcpciPortControllerAlertVbusVoltageAlarmHi, UcmTcpciPortControllerAlertVbusVoltageAlarmLo, _UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE, buses.ucmtcpci_port_controller_alert_type, ucmtcpciportcontroller/UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE, ucmtcpciportcontroller/UcmTcpciPortControllerAlertCCStatus, ucmtcpciportcontroller/UcmTcpciPortControllerAlertFault, ucmtcpciportcontroller/UcmTcpciPortControllerAlertInvalid, ucmtcpciportcontroller/UcmTcpciPortControllerAlertPowerStatus, ucmtcpciportcontroller/UcmTcpciPortControllerAlertReceiveSOPMessageStatus, ucmtcpciportcontroller/UcmTcpciPortControllerAlertReceivedHardReset, ucmtcpciportcontroller/UcmTcpciPortControllerAlertRxBufferOverflow, ucmtcpciportcontroller/UcmTcpciPortControllerAlertTransmitSOPMessageDiscarded, ucmtcpciportcontroller/UcmTcpciPortControllerAlertTransmitSOPMessageFailed, ucmtcpciportcontroller/UcmTcpciPortControllerAlertTransmitSOPMessageSuccessful, ucmtcpciportcontroller/UcmTcpciPortControllerAlertVbusSinkDisconnectDetected, ucmtcpciportcontroller/UcmTcpciPortControllerAlertVbusVoltageAlarmHi, ucmtcpciportcontroller/UcmTcpciPortControllerAlertVbusVoltageAlarmLo
ms.topic: enum
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
-	UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE
product:
- Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE
---

# _UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE enumeration


## -description



                    
                Defines generic alert values that are used to indicate the type of hardware alert received on the port controller.


## -enum-fields




### -field UcmTcpciPortControllerAlertInvalid


                        
                    The alert is invalid.


### -field UcmTcpciPortControllerAlertCCStatus

Indicates a
                        
                    CC status change alert.


### -field UcmTcpciPortControllerAlertPowerStatus

Indicates a
                        
                    power status change alert.
                        
                    


### -field UcmTcpciPortControllerAlertReceiveSOPMessageStatus


                        
                    Indicates an SOP message alert.


### -field UcmTcpciPortControllerAlertReceivedHardReset


                        
                    Indicates a hard Reset alert.


### -field UcmTcpciPortControllerAlertTransmitSOPMessageFailed


                        
                    Indicates that the SOP message transmission was not successful.


### -field UcmTcpciPortControllerAlertTransmitSOPMessageDiscarded

Indicates that the
                        
                    SOP message transmission was not sent due to an incoming receive message. 


### -field UcmTcpciPortControllerAlertTransmitSOPMessageSuccessful


                        
                    Indicates that the SOP message transmission was successful.


### -field UcmTcpciPortControllerAlertVbusVoltageAlarmHi


                        
                    Indicates a high-voltage alarm.


### -field UcmTcpciPortControllerAlertVbusVoltageAlarmLo


                        
                    Indicates a low-voltage alarm.


### -field UcmTcpciPortControllerAlertFault


                        
                    Indicates that a Fault has occurred. 


### -field UcmTcpciPortControllerAlertRxBufferOverflow

Indicates that the
                        
                     TCPC Rx buffer has overflowed.


### -field UcmTcpciPortControllerAlertVbusSinkDisconnectDetected


                        
                    Indicates that a VBUS Sink Disconnect Threshold crossing has been detected 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt805898">UCMTCPCI_PORT_CONTROLLER_ALERT_DATA</a>
 

 

