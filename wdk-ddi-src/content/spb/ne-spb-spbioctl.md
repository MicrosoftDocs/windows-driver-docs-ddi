---
UID: NE:spb.SpbIoctl
title: SpbIoctl (spb.h)
description: Defines values to indicate the type I/O control request.
old-location: spb\spbioctl.htm
tech.root: SPB
ms.date: 11/11/2021
keywords: ["SpbIoctl enumeration"]
ms.keywords: "*PSpbIoctl, *PSpbIoctl enumeration [Buses], IOCTL_SPB_EXECUTE_SEQUENCE, IOCTL_SPB_FULL_DUPLEX, IOCTL_SPB_LOCK_CONNECTION, IOCTL_SPB_LOCK_CONTROLLER, IOCTL_SPB_UNLOCK_CONNECTION, IOCTL_SPB_UNLOCK_CONTROLLER, SPB.spbioctl, SpbIoctl, SpbIoctl enumeration [Buses], spb/*PSpbIoctl, spb/IOCTL_SPB_EXECUTE_SEQUENCE, spb/IOCTL_SPB_FULL_DUPLEX, spb/IOCTL_SPB_LOCK_CONNECTION, spb/IOCTL_SPB_LOCK_CONTROLLER, spb/IOCTL_SPB_UNLOCK_CONNECTION, spb/IOCTL_SPB_UNLOCK_CONTROLLER, spb/SpbIoctl"
req.header: spb.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
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
targetos: Windows
req.typenames: SpbIoctl, *PSpbIoctl
f1_keywords:
 - SpbIoctl
 - spb/SpbIoctl
 - PSpbIoctl
 - spb/PSpbIoctl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Spb.h
api_name:
 - SpbIoctl
 - PSpbIoctl
---

# SpbIoctl enumeration

## -description

Defines values to indicate the type I/O control request.

## -enum-fields

### -field IOCTL_SPB_LOCK_CONTROLLER

The [IOCTL_SPB_LOCK_CONTROLLER](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_lock_controller-control-code) control code is used by a client (peripheral driver) to lock the SPB controller. While the controller is locked, the client has exclusive use of the bus to access the specified target device for the lock.

### -field IOCTL_SPB_UNLOCK_CONTROLLER

The [IOCTL_SPB_UNLOCK_CONTROLLER](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_unlock_controller-control-code) I/O control code is used by a client (peripheral driver) to unlock the SPB controller. The client previously locked the controller to gain exclusive use of the bus to access a target device on the bus.

### -field IOCTL_SPB_EXECUTE_SEQUENCE

The [IOCTL_SPB_EXECUTE_SEQUENCE](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_execute_sequence) I/O control code enables a client (peripheral driver) of the SPB controller driver to perform a sequence of transfers (reads and writes) as a single, atomic operation with one I/O request. The designated device on the bus is the target for all transfers in the sequence.

### -field IOCTL_SPB_LOCK_CONNECTION

The [IOCTL_SPB_LOCK_CONNECTION](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_lock_connection-control-code) control code is used by a client (peripheral driver) to acquire the connection lock on an SPB-connected target device that is shared with another client. While a client holds the connection lock,  this client has exclusive access to the device.

### -field IOCTL_SPB_UNLOCK_CONNECTION

The [IOCTL_SPB_UNLOCK_CONNECTION](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_unlock_connection-control-code) I/O control code is used by a client (peripheral driver) to release the connection lock on an SPB-connected target device that is shared with another client. The client previously sent an [IOCTL_SPB_LOCK_CONNECTION](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_lock_connection-control-code) request to acquire exclusive access to the device.

### -field IOCTL_SPB_FULL_DUPLEX

The [IOCTL_SPB_FULL_DUPLEX](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_full_duplex-control-code) control code is used by a client (peripheral driver) to request a full-duplex I/O operation. Full-duplex I/O operations are supported by controllers for buses such as SPI that can simultaneously read and write data.

### -field IOCTL_SPB_MULTI_SPI_TRANSFER

The **IOCTL_SPB_MULTI_SPI_TRANSFER** control code is used by a client (peripheral driver) to request a SPI I/O operation to use a multi-SPI transfer mode such as Dual or Quad SPI. Multi-SPI I/O operations are supported by controllers for SPI buses that support data transfer in Dual or Quad SPI line modes.
