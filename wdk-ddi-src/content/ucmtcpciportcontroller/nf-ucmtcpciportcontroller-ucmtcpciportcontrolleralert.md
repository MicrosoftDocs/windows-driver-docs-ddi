---
UID: NF:ucmtcpciportcontroller.UcmTcpciPortControllerAlert
title: UcmTcpciPortControllerAlert function (ucmtcpciportcontroller.h)
description: Sends information about the hardware alerts that are received on the port controller to UcmTcpciCx.
old-location: buses\ucmtcpciportcontrolleralert.htm
tech.root: usbref
ms.date: 01/05/2022
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

### -param PortControllerObject [in]

Handle to the port controller object that the client driver received in the previous call to [UcmTcpciPortControllerCreate](./nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate.md).

### -param AlertData

A pointer to an array of [UCMTCPCI_PORT_CONTROLLER_ALERT_DATA](./ns-ucmtcpciportcontroller-_ucmtcpci_port_controller_alert_data.md) that contains all current alerts that have not been sent to UcmTcpciCx. This value cannot be NULL.

### -param NumberOfAlerts

The number of items in the array pointed to by *AlertData*. This value cannot be 0.

## -remarks

**UcmTcpciPortControllerAlert** returns STATUS_SUCCESS if the operation succeeds. Otherwise, this inline function may return an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) error code.

The client driver must call **UcmTcpciPortControllerAlert** that has been previously started by calling [UcmTcpciPortControllerStart](./nf-ucmtcpciportcontroller-ucmtcpciportcontrollerstart.md).

When a hardware alert occurs, the client driver must determine the type of alerts, fetch any auxiliary information associated with that alert, such as a PD message, populate the array, and then call **UcmTcpciPortControllerAlert**.

The client driver must report the alerts sequentially. The driver must not call this method on threads that are running simultaneously as that can lead to race conditions. Even though the class extension ensures that all internal data is correctly lock-protected, if the driver calls **UcmTcpciPortControllerAlert** from multiple threads at the same time without any external synchronization, it is not guaranteed that set of received alerts is current. To avoid that scenario, the driver must call this method within the [Interrupt Service Routine](/windows-hardware/drivers/kernel/interrupt-service-routines) (ISR)or a [DPC object](/windows-hardware/drivers/kernel/dpc-objects-and-dpcs) that is queued for the ISR. The ISR should be  synchronized correctly to have only one instance running at any given time. 

The client driver must assume that the class extension may submit requests before **UcmTcpciPortControllerAlert** returns, from within this call. 

When handling alerts, UcmTcpciCx may send hardware requests to the client driver before the **UcmTcpciPortControllerAlert** call returns. If the driver holds a lock while calling **UcmTcpciPortControllerAlert** and also attempts to acquire the same lock when handling the hardware request, deadlock can occur.

## -see-also

- [Handling Hardware Interrupts](/windows-hardware/drivers/wdf/handling-hardware-interrupts)