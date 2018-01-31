---
UID: NE:ucmtcpciportcontroller._UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE
title: "_UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE"
author: windows-driver-content
description: Defines generic alert values that are used to indicate the type of hardware alert received on the port controller.
old-location: buses\ucmtcpci_port_controller_alert_type.htm
old-project: usbref
ms.assetid: 77162a25-b5aa-45d0-ac4d-6500df9782de
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE, ucmtcpciportcontroller/UcmTcpciPortControllerAlertVbusSinkDisconnectDetected, ucmtcpciportcontroller/UcmTcpciPortControllerAlertCCStatus, ucmtcpciportcontroller/UcmTcpciPortControllerAlertFault, ucmtcpciportcontroller/UcmTcpciPortControllerAlertTransmitSOPMessageDiscarded, _UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE, UcmTcpciPortControllerAlertReceiveSOPMessageStatus, UcmTcpciPortControllerAlertInvalid, UcmTcpciPortControllerAlertReceivedHardReset, ucmtcpciportcontroller/UcmTcpciPortControllerAlertVbusVoltageAlarmLo, UcmTcpciPortControllerAlertTransmitSOPMessageDiscarded, ucmtcpciportcontroller/UcmTcpciPortControllerAlertPowerStatus, UcmTcpciPortControllerAlertTransmitSOPMessageSuccessful, ucmtcpciportcontroller/UcmTcpciPortControllerAlertReceivedHardReset, UcmTcpciPortControllerAlertVbusSinkDisconnectDetected, UcmTcpciPortControllerAlertVbusVoltageAlarmLo, ucmtcpciportcontroller/UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE, ucmtcpciportcontroller/UcmTcpciPortControllerAlertRxBufferOverflow, buses.ucmtcpci_port_controller_alert_type, UcmTcpciPortControllerAlertTransmitSOPMessageFailed, UcmTcpciPortControllerAlertFault, UcmTcpciPortControllerAlertPowerStatus, UcmTcpciPortControllerAlertCCStatus, ucmtcpciportcontroller/UcmTcpciPortControllerAlertTransmitSOPMessageSuccessful, UcmTcpciPortControllerAlertVbusVoltageAlarmHi, ucmtcpciportcontroller/UcmTcpciPortControllerAlertReceiveSOPMessageStatus, UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE enumeration [Buses], ucmtcpciportcontroller/UcmTcpciPortControllerAlertInvalid, ucmtcpciportcontroller/UcmTcpciPortControllerAlertTransmitSOPMessageFailed, UcmTcpciPortControllerAlertRxBufferOverflow, ucmtcpciportcontroller/UcmTcpciPortControllerAlertVbusVoltageAlarmHi
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




#### - UcmTcpciPortControllerAlertInvalid


                        
                    The alert is invalid.


#### - UcmTcpciPortControllerAlertCCStatus

Indicates a
                        
                    CC status change alert.


#### - UcmTcpciPortControllerAlertPowerStatus

Indicates a
                        
                    power status change alert.
                        
                    


#### - UcmTcpciPortControllerAlertReceiveSOPMessageStatus


                        
                    Indicates an SOP message alert.


#### - UcmTcpciPortControllerAlertReceivedHardReset


                        
                    Indicates a hard Reset alert.


#### - UcmTcpciPortControllerAlertTransmitSOPMessageFailed


                        
                    Indicates that the SOP message transmission was not successful.


#### - UcmTcpciPortControllerAlertTransmitSOPMessageDiscarded

Indicates that the
                        
                    SOP message transmission was not sent due to an incoming receive message. 


#### - UcmTcpciPortControllerAlertTransmitSOPMessageSuccessful


                        
                    Indicates that the SOP message transmission was successful.


#### - UcmTcpciPortControllerAlertVbusVoltageAlarmHi


                        
                    Indicates a high-voltage alarm.


#### - UcmTcpciPortControllerAlertVbusVoltageAlarmLo


                        
                    Indicates a low-voltage alarm.


#### - UcmTcpciPortControllerAlertFault


                        
                    Indicates that a Fault has occurred. 


#### - UcmTcpciPortControllerAlertRxBufferOverflow

Indicates that the
                        
                     TCPC Rx buffer has overflowed.


#### - UcmTcpciPortControllerAlertVbusSinkDisconnectDetected


                        
                    Indicates that a VBUS Sink Disconnect Threshold crossing has been detected 


## -see-also

<a href="..\ucmtcpciportcontroller\ns-ucmtcpciportcontroller-_ucmtcpci_port_controller_alert_data.md">UCMTCPCI_PORT_CONTROLLER_ALERT_DATA</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

