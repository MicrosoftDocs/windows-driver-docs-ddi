---
UID: NF:ucmtcpciportcontroller.UcmTcpciPortControllerAlert
title: UcmTcpciPortControllerAlert function (ucmtcpciportcontroller.h)
description: Sends information about the hardware alerts that are received on the port controller to UcmTcpciCx.
old-location: buses\ucmtcpciportcontrolleralert.htm
tech.root: usbref
ms.assetid: 38700667-d872-4c08-b846-236e94318dba
ms.date: 05/07/2018
keywords: ["UcmTcpciPortControllerAlert function"]
ms.keywords: UcmTcpciPortControllerAlert, UcmTcpciPortControllerAlert method [Buses], buses.ucmtcpciportcontrolleralert, ucmtcpciportcontroller/UcmTcpciPortControllerAlert
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - UcmTcpciPortControllerAlert
 - ucmtcpciportcontroller/UcmTcpciPortControllerAlert
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ucmtcpciportcontroller.h
api_name:
 - UcmTcpciPortControllerAlert
---

# UcmTcpciPortControllerAlert function


## -description

                Sends information about the hardware alerts that are received on the port controller to UcmTcpciCx.

## -parameters

### -param PortControllerObject 

[in]
Handle to the port controller object that the client driver received in the previous call to <a href="/windows-hardware/drivers/ddi/ucmtcpciportcontroller/nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate">UcmTcpciPortControllerCreate</a>.

### -param AlertData

A pointer to an array of <a href="/windows-hardware/drivers/ddi/ucmtcpciportcontroller/ns-ucmtcpciportcontroller-_ucmtcpci_port_controller_alert_data">UCMTCPCI_PORT_CONTROLLER_ALERT_DATA</a> that contains all current alerts that have not been sent to UcmTcpciCx. This value cannot be NULL.

### -param NumberOfAlerts

The number of items in the array pointed to by <i>AlertData</i>. This value cannot be 0.

## -returns

(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.

## -remarks

The client driver must call <b>UcmTcpciPortControllerAlert</b> that has been previously started by calling <a href="/windows-hardware/drivers/ddi/ucmtcpciportcontroller/nf-ucmtcpciportcontroller-ucmtcpciportcontrollerstart">UcmTcpciPortControllerStart</a>.

When a hardware alert occurs, the client driver must determine the type of alerts, fetch any auxiliary information associated with that alert, such as a PD message, populate the array, and then call <b>UcmTcpciPortControllerAlert</b>.

The client driver must report the alerts sequentially. The driver must not call this method on threads that are running simultaneously as that can lead to race conditions. Even though the class extension ensures that all internal data is correctly lock-protected, if the driver calls <b>UcmTcpciPortControllerAlert</b> from multiple threads at the same time without any external synchronization, it is not guaranteed that set of received alerts is current. To avoid that scenario, the driver must call this method within the <a href="/windows-hardware/drivers/kernel/interrupt-service-routines">Interrupt Service Routine</a> (ISR)or a <a href="/windows-hardware/drivers/kernel/dpc-objects-and-dpcs">DPC object</a> that is queued for the ISR. The ISR should be  synchronized correctly to have only one instance running at any given time. 

The client driver must assume that the class extension may submit requests before <b>UcmTcpciPortControllerAlert</b> returns, from within this call. 

When handling alerts, UcmTcpciCx may send hardware requests to the client driver before the <b>UcmTcpciPortControllerAlert</b> call returns. If the driver holds a lock while calling <b>UcmTcpciPortControllerAlert</b> and also attempts to acquire the same lock when handling the hardware request, deadlock can occur.

## -see-also

<a href="/windows-hardware/drivers/wdf/handling-hardware-interrupts">Handling Hardware Interrupts</a>