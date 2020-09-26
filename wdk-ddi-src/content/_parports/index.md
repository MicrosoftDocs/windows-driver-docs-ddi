---
UID: TP:parports
title: Parallel Ports
ms.assetid: 38f4cf0c-2fc1-3909-83b7-bf354cf904c1
ms.date: 05/09/2018
keywords: ["Parallel Ports"]
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Parallel Ports

## -description

Overview of the Parallel Ports technology.

To develop Parallel Ports, you need these headers:

* [gpio.h](../gpio/index.md)
* [gpioclx.h](../gpioclx/index.md)
* [ntddpar.h](../ntddpar/index.md)
* [ntddser.h](../ntddser/index.md)
* [parallel.h](../parallel/index.md)

For the programming guide, see [Parallel Ports](/windows-hardware/drivers/parports).

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_IEEE1284_GET_MODE IOCTL](../ntddpar/ni-ntddpar-ioctl_ieee1284_get_mode.md) | The IOCTL_IEEE1284_GET_MODE request returns the IEEE 1284 read and write protocols that are currently set for a parallel device. |
| [IOCTL_IEEE1284_NEGOTIATE IOCTL](../ntddpar/ni-ntddpar-ioctl_ieee1284_negotiate.md) | The IOCTL_IEEE1284_NEGOTIATE request sets the read and write protocols that are used for a parallel device. |
| [IOCTL_INTERNAL_DESELECT_DEVICE IOCTL](../parallel/ni-parallel-ioctl_internal_deselect_device.md) | The IOCTL_INTERNAL_DESELECT_DEVICE request deselects an IEEE 1284.3 daisy-chain device or an IEEE 1284 end-of-chain device attached to a parallel port. |
| [IOCTL_INTERNAL_DISCONNECT_IDLE IOCTL](../parallel/ni-parallel-ioctl_internal_disconnect_idle.md) | The IOCTL_INTERNAL_DISCONNECT_IDLE request disconnects the IEEE 1284 operating modes that are set for a parallel device. |
| [IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO IOCTL](../parallel/ni-parallel-ioctl_internal_get_more_parallel_port_info.md) | The IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO request returns information about a parallel port. |
| [IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO IOCTL](../parallel/ni-parallel-ioctl_internal_get_parallel_pnp_info.md) | The IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO request returns Plug and Play information about a parallel port. |
| [IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO IOCTL](../parallel/ni-parallel-ioctl_internal_get_parallel_port_info.md) | The IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO request returns information about a parallel port. |
| [IOCTL_INTERNAL_INIT_1284_3_BUS IOCTL](../parallel/ni-parallel-ioctl_internal_init_1284_3_bus.md) | The IOCTL_INTERNAL_INIT_1284_3_BUS request initializes and assigns an IEEE 1284.3 device ID to all the 1284.3 daisy chain devices that are attached to a parallel port. |
| [IOCTL_INTERNAL_LOCK_PORT IOCTL](../parallel/ni-parallel-ioctl_internal_lock_port.md) | The IOCTL_INTERNAL_LOCK_PORT request allocates the parallel device's parent parallel port and selects the parallel device on the port. |
| [IOCTL_INTERNAL_LOCK_PORT_NO_SELECT IOCTL](../parallel/ni-parallel-ioctl_internal_lock_port_no_select.md) | The IOCTL_INTERNAL_LOCK_PORT_NO_SELECT request allocates the parallel device's parent parallel port, but does not select the parallel device. |
| [IOCTL_INTERNAL_PARALLEL_CLEAR_CHIP_MODE IOCTL](../parallel/ni-parallel-ioctl_internal_parallel_clear_chip_mode.md) | The IOCTL_INTERNAL_PARALLEL_CLEAR_CHIP_MODE request clears the operating mode of a parallel port. |
| [IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT IOCTL](../parallel/ni-parallel-ioctl_internal_parallel_connect_interrupt.md) | The IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT request connects an optional interrupt service routine and an optional deferred port check routine to a parallel port. |
| [IOCTL_INTERNAL_PARALLEL_DISCONNECT_INTERRUPT IOCTL](../parallel/ni-parallel-ioctl_internal_parallel_disconnect_interrupt.md) | The IOCTL_INTERNAL_PARALLEL_DISCONNECT_INTERRUPT request disconnects an interrupt service routine (and an optional deferred port check service routine) that was connected by using an IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT request. |
| [IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE IOCTL](../parallel/ni-parallel-ioctl_internal_parallel_port_allocate.md) | The IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE request allocates a parallel port for exclusive access by a client. |
| [IOCTL_INTERNAL_PARALLEL_PORT_FREE IOCTL](../parallel/ni-parallel-ioctl_internal_parallel_port_free.md) | The IOCTL_INTERNAL_PARALLEL_PORT_FREE request frees a parallel port. |
| [IOCTL_INTERNAL_PARALLEL_SET_CHIP_MODE IOCTL](../parallel/ni-parallel-ioctl_internal_parallel_set_chip_mode.md) | The IOCTL_INTERNAL_PARALLEL_SET_CHIP_MODE request sets the operating mode of a parallel port. |
| [IOCTL_INTERNAL_PARCLASS_CONNECT IOCTL](../parallel/ni-parallel-ioctl_internal_parclass_connect.md) | The IOCTL_INTERNAL_PARCLASS_CONNECT request returns information about a parallel port and the callback routines that the system-supplied bus driver for parallel ports provides to operate the parallel port. |
| [IOCTL_INTERNAL_PARCLASS_DISCONNECT IOCTL](../parallel/ni-parallel-ioctl_internal_parclass_disconnect.md) | The IOCTL_INTERNAL_PARCLASS_DISCONNECT request disconnects a client from a parallel device. |
| [IOCTL_INTERNAL_RELEASE_PARALLEL_PORT_INFO IOCTL](../parallel/ni-parallel-ioctl_internal_release_parallel_port_info.md) | The IOCTL_INTERNAL_RELEASE_PARALLEL_PORT_INFO request returns STATUS_SUCCESS. |
| [IOCTL_INTERNAL_SELECT_DEVICE IOCTL](../parallel/ni-parallel-ioctl_internal_select_device.md) | The IOCTL_INTERNAL_SELECT_DEVICE request |
| [IOCTL_INTERNAL_UNLOCK_PORT IOCTL](../parallel/ni-parallel-ioctl_internal_unlock_port.md) | The IOCTL_INTERNAL_UNLOCK_PORT request deselects a parallel device and frees the parallel device's parent parallel port. |
| [IOCTL_INTERNAL_UNLOCK_PORT_NO_DESELECT IOCTL](../parallel/ni-parallel-ioctl_internal_unlock_port_no_deselect.md) | The IOCTL_INTERNAL_UNLOCK_PORT_NO_DESELECT request frees a parallel device's parent parallel port. |
| [IOCTL_PAR_GET_DEFAULT_MODES IOCTL](../ntddpar/ni-ntddpar-ioctl_par_get_default_modes.md) | The IOCTL_PAR_GET_DEFAULT_MODES request returns the default write (forward) and read (reverse) IEEE 1284 protocols that the system-supplied bus driver for parallel ports uses. |
| [IOCTL_PAR_GET_DEVICE_CAPS IOCTL](../ntddpar/ni-ntddpar-ioctl_par_get_device_caps.md) | The IOCTL_PAR_GET_DEVICE_CAPS request does the following |
| [IOCTL_PAR_IS_PORT_FREE IOCTL](../ntddpar/ni-ntddpar-ioctl_par_is_port_free.md) | The IOCTL_PAR_IS_PORT_FREE request determines if a parallel device's parent parallel port is free at the time the system-supplied bus driver for parallel ports processes the request. |
| [IOCTL_PAR_QUERY_DEVICE_ID IOCTL](../ntddpar/ni-ntddpar-ioctl_par_query_device_id.md) | The IOCTL_PAR_QUERY_DEVICE_ID request returns the IEEE 1284 device ID of a parallel device assigned by the system-supplied function driver for parallel ports. |
| [IOCTL_PAR_QUERY_DEVICE_ID_SIZE IOCTL](../ntddpar/ni-ntddpar-ioctl_par_query_device_id_size.md) | The IOCTL_PAR_QUERY_DEVICE_ID_SIZE request returns the size, in bytes, of a buffer that can hold a device's IEEE 1284 device ID and a NULL terminator. |
| [IOCTL_PAR_QUERY_INFORMATION IOCTL](../ntddpar/ni-ntddpar-ioctl_par_query_information.md) | The IOCTL_PAR_QUERY_INFORMATION request returns the status of an IEEE 1284 end-of-chain device. |
| [IOCTL_PAR_QUERY_LOCATION IOCTL](../ntddpar/ni-ntddpar-ioctl_par_query_location.md) | The IOCTL_PAR_QUERY_LOCATION request returns the &#0034;LPTn&#0034; or &#0034;LPTn.m&#0034; symbolic link name associated with a parallel device. |
| [IOCTL_PAR_QUERY_RAW_DEVICE_ID IOCTL](../ntddpar/ni-ntddpar-ioctl_par_query_raw_device_id.md) | The IOCTL_PAR_QUERY_RAW_DEVICE_ID request returns a raw device ID, which includes the following |
| [IOCTL_PAR_SET_INFORMATION IOCTL](../ntddpar/ni-ntddpar-ioctl_par_set_information.md) | The IOCTL_PAR_SET_INFORMATION request resets and initializes a parallel device. |
| [IOCTL_PAR_SET_READ_ADDRESS IOCTL](../ntddpar/ni-ntddpar-ioctl_par_set_read_address.md) | The IOCTL_PAR_SET_READ_ADDRESS request sets an extended capabilities port (ECP) or enhanced parallel port (EPP) read address (channel) for a parallel device. |
| [IOCTL_PAR_SET_WRITE_ADDRESS IOCTL](../ntddpar/ni-ntddpar-ioctl_par_set_write_address.md) | The IOCTL_PAR_SET_WRITE_ADDRESS request sets an extended capabilities port (ECP) or enhanced parallel port (EPP) write address (channel) for a parallel device. The parallel port bus driver queues this request on a work queue for the parallel device. |