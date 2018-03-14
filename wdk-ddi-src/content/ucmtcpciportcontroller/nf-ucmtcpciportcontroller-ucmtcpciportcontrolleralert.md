---
UID: NF:ucmtcpciportcontroller.UcmTcpciPortControllerAlert
title: UcmTcpciPortControllerAlert function
author: windows-driver-content
description: Sends information about the hardware alerts that are received on the port controller to UcmTcpciCx.
old-location: buses\ucmtcpciportcontrolleralert.htm
old-project: usbref
ms.assetid: 38700667-d872-4c08-b846-236e94318dba
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UcmTcpciPortControllerAlert, UcmTcpciPortControllerAlert method [Buses], buses.ucmtcpciportcontrolleralert, ucmtcpciportcontroller/UcmTcpciPortControllerAlert
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
req.lib: 
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ucmtcpciportcontroller.h
api_name:
-	UcmTcpciPortControllerAlert
product: Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE
req.product: Windows 10 or later.
---

# UcmTcpciPortControllerAlert function


## -description




                Sends information about the hardware alerts that are received on the port controller to UcmTcpciCx. 


## -syntax


````
VOID UcmTcpciPortControllerAlert(
  _In_ UCMTCPCIPORTCONTROLLER               PortControllerObject,
       PUCMTCPCI_PORT_CONTROLLER_ALERT_DATA AlertData,
       size_t                               NumberOfAlerts
);
````


## -parameters




### -param PortControllerObject [in]

Handle to the port controller object that the client driver received in the previous call to <a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate.md">UcmTcpciPortControllerCreate</a>.


### -param AlertData

A pointer to an array of <a href="..\ucmtcpciportcontroller\ns-ucmtcpciportcontroller-_ucmtcpci_port_controller_alert_data.md">UCMTCPCI_PORT_CONTROLLER_ALERT_DATA</a> that contains all current alerts that have not been sent to UcmTcpciCx. This value cannot be NULL.


### -param NumberOfAlerts

The number of items in the array pointed to by <i>AlertData</i>. This value cannot be 0.


## -returns




(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.
                    




## -remarks



The client driver must call <b>UcmTcpciPortControllerAlert</b> that has been previously started by calling <a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrollerstart.md">UcmTcpciPortControllerStart</a>.

When a hardware alert occurs, the client driver must determine the type of alerts, fetch any auxiliary information associated with that alert, such as a PD message, populate the array, and then call <b>UcmTcpciPortControllerAlert</b>.

The client driver must report the alerts sequentially. The driver must not call this method on threads that are running simultaneously as that can lead to race conditions. Even though the class extension ensures that all internal data is correctly lock-protected, if the driver calls <b>UcmTcpciPortControllerAlert</b> from multiple threads at the same time without any external synchronization, it is not guaranteed that set of received alerts is current. To avoid that scenario, the driver must call this method within the <a href="https://msdn.microsoft.com/d72a15be-772f-4cd4-a304-10981056d735">Interrupt Service Routine</a> (ISR)or a <a href="https://msdn.microsoft.com/962e6b38-afed-4711-a556-ed9cbc139a1a">DPC object</a> that is queued for the ISR. The ISR should be  synchronized correctly to have only one instance running at any given time. 

The client driver must assume that the class extension may submit requests before <b>UcmTcpciPortControllerAlert</b> returns, from within this call. 

When handling alerts, UcmTcpciCx may send hardware requests to the client driver before the <b>UcmTcpciPortControllerAlert</b> call returns. If the driver holds a lock while calling <b>UcmTcpciPortControllerAlert</b> and also attempts to acquire the same lock when handling the hardware request, deadlock can occur.




## -see-also

<a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/wdf/handling-hardware-interrupts">Handling Hardware Interrupts</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UcmTcpciPortControllerAlert method%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

