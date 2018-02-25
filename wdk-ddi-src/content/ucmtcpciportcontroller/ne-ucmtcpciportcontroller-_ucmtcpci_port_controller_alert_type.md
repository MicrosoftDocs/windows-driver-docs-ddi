---
UID: NE:ucmtcpciportcontroller._UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE
title: "_UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE"
author: windows-driver-content
description: Defines generic alert values that are used to indicate the type of hardware alert received on the port controller.
old-location: buses\ucmtcpci_port_controller_alert_type.htm
old-project: UsbRef
ms.assetid: 77162a25-b5aa-45d0-ac4d-6500df9782de
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ",  , ,, A, C, E, I, L, M, N, O, P, R, T, U, UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE, UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE enumeration [Buses], UcmTcpciPortControllerAlertCCStatus, UcmTcpciPortControllerAlertFault, UcmTcpciPortControllerAlertInvalid, UcmTcpciPortControllerAlertPowerStatus, UcmTcpciPortControllerAlertReceiveSOPMessageStatus, UcmTcpciPortControllerAlertReceivedHardReset, UcmTcpciPortControllerAlertRxBufferOverflow, UcmTcpciPortControllerAlertTransmitSOPMessageDiscarded, UcmTcpciPortControllerAlertTransmitSOPMessageFailed, UcmTcpciPortControllerAlertTransmitSOPMessageSuccessful, UcmTcpciPortControllerAlertVbusSinkDisconnectDetected, UcmTcpciPortControllerAlertVbusVoltageAlarmHi, UcmTcpciPortControllerAlertVbusVoltageAlarmLo, Y, _, _UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE, buses.ucmtcpci_port_controller_alert_type, ucmtcpciportcontroller/UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE, ucmtcpciportcontroller/UcmTcpciPortControllerAlertCCStatus, ucmtcpciportcontroller/UcmTcpciPortControllerAlertFault, ucmtcpciportcontroller/UcmTcpciPortControllerAlertInvalid, ucmtcpciportcontroller/UcmTcpciPortControllerAlertPowerStatus, ucmtcpciportcontroller/UcmTcpciPortControllerAlertReceiveSOPMessageStatus, ucmtcpciportcontroller/UcmTcpciPortControllerAlertReceivedHardReset, ucmtcpciportcontroller/UcmTcpciPortControllerAlertRxBufferOverflow, ucmtcpciportcontroller/UcmTcpciPortControllerAlertTransmitSOPMessageDiscarded, ucmtcpciportcontroller/UcmTcpciPortControllerAlertTransmitSOPMessageFailed, ucmtcpciportcontroller/UcmTcpciPortControllerAlertTransmitSOPMessageSuccessful, ucmtcpciportcontroller/UcmTcpciPortControllerAlertVbusSinkDisconnectDetected, ucmtcpciportcontroller/UcmTcpciPortControllerAlertVbusVoltageAlarmHi, ucmtcpciportcontroller/UcmTcpciPortControllerAlertVbusVoltageAlarmLo"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ucmtcpciportcontroller.h
apiname:
-	UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE
product: Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE
req.product: Windows 10 or later.
---

# _UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE enumeration


## -description



                    
                Defines generic alert values that are used to indicate the type of hardware alert received on the port controller.


## -syntax


````
typedef enum _UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE { 
  UcmTcpciPortControllerAlertInvalid                       = = 0x0,
  UcmTcpciPortControllerAlertCCStatus,
  UcmTcpciPortControllerAlertPowerStatus,
  UcmTcpciPortControllerAlertReceiveSOPMessageStatus,
  UcmTcpciPortControllerAlertReceivedHardReset,
  UcmTcpciPortControllerAlertTransmitSOPMessageFailed,
  UcmTcpciPortControllerAlertTransmitSOPMessageDiscarded,
  UcmTcpciPortControllerAlertTransmitSOPMessageSuccessful,
  UcmTcpciPortControllerAlertVbusVoltageAlarmHi,
  UcmTcpciPortControllerAlertVbusVoltageAlarmLo,
  UcmTcpciPortControllerAlertFault,
  UcmTcpciPortControllerAlertRxBufferOverflow,
  UcmTcpciPortControllerAlertVbusSinkDisconnectDetected
} UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE;
````


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

<a href="..\ucmtcpciportcontroller\ns-ucmtcpciportcontroller-_ucmtcpci_port_controller_alert_data.md">UCMTCPCI_PORT_CONTROLLER_ALERT_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE enumeration%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

