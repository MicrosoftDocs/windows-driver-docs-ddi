---
UID: TP:parports
author: windows-driver-content
ms.assetid: 38f4cf0c-2fc1-3909-83b7-bf354cf904c1
ms.author: windowsdriverdev
ms.date: 05/09/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Parallel Ports

## -description

Overview of the Parallel Ports technology.

To develop Parallel Ports, you need these headers:

 * [gpio.h](..\gpio\index.md)
 * [gpioclx.h](..\gpioclx\index.md)
 * [ntddpar.h](..\ntddpar\index.md)
 * [ntddser.h](..\ntddser\index.md)
 * [parallel.h](..\parallel\index.md)

For the programming guide, see [Parallel Ports](https://docs.microsoft.com/en-us/windows-hardware/drivers/parports).

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [PDETERMINE_IEEE_MODES callback](..\parallel\nc-parallel-pdetermine_ieee_modes.md) | The PDETERMINE_IEEE_MODES-typed callback routine determines which IEEE 1284 protocols a parallel device supports. The system-supplied bus driver for parallel ports supplies this routine. |
| [PNEGOTIATE_IEEE_MODE callback](..\parallel\nc-parallel-pnegotiate_ieee_mode.md) | The PNEGOTIATE_IEEE_MODE-typed callback routine selects the fastest forward and reverse protocols that the system-supplied bus driver for parallel ports supports from among those specified by the caller. |
| [PPARALLEL_CLEAR_CHIP_MODE callback](..\parallel\nc-parallel-pparallel_clear_chip_mode.md) | The PPARALLEL_CLEAR_CHIP_MODE-typed callback routine clears the operating mode of a parallel port by resetting the communication mode of the host chipset to IEEE 1284-compatibility mode. |
| [PPARALLEL_DESELECT_ROUTINE callback](..\parallel\nc-parallel-pparallel_deselect_routine.md) | The PPARALLEL_DESELECT_ROUTINE-typed callback routine deselects either an IEEE 1284.3 daisy chain device or an IEEE 1284 end-of-chain device that is attached to a parallel port. |
| [PPARALLEL_FREE_ROUTINE callback](..\parallel\nc-parallel-pparallel_free_routine.md) | The PPARALLEL_FREE_ROUTINE-typed callback routine frees a parallel port. The system-supplied function driver for parallel ports supplies this routine. |
| [PPARALLEL_IEEE_FWD_TO_REV callback](..\parallel\nc-parallel-pparallel_ieee_fwd_to_rev.md) | The PPARALLEL_IEEE_FWD_TO_REV-typed callback routine changes the transfer mode from forward to reverse. The system-supplied bus driver for parallel ports supplies this routine. |
| [PPARALLEL_IEEE_REV_TO_FWD callback](..\parallel\nc-parallel-pparallel_ieee_rev_to_fwd.md) | The PPARALLEL_IEEE_REV_TO_FWD-typed callback routine changes the transfer mode from reverse to forward. The system-supplied bus driver for parallel ports supplies this routine. |
| [PPARALLEL_QUERY_WAITERS_ROUTINE callback](..\parallel\nc-parallel-pparallel_query_waiters_routine.md) | The PPARALLEL_QUERY_WAITERS_ROUTINE-typed callback routine returns the number of IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE and IOCTL_INTERNAL_SELECT_DEVICE requests that are queued on the work queue of a parallel port. |
| [PPARALLEL_READ callback](..\parallel\nc-parallel-pparallel_read.md) | The PPARALLEL_READ-typed callback routine reads data from a parallel device. The system-supplied bus driver for parallel ports supplies this routine. |
| [PPARALLEL_SET_CHIP_MODE callback](..\parallel\nc-parallel-pparallel_set_chip_mode.md) | The PPARALLEL_SET_CHIP_MODE-typed callback routine sets the operating mode of a parallel port. The system-supplied function driver for parallel ports supplies this routine. |
| [PPARALLEL_TRY_ALLOCATE_ROUTINE callback](..\parallel\nc-parallel-pparallel_try_allocate_routine.md) | The PPARALLEL_TRY_ALLOCATE_ROUTINE-typed (ISR) callback routine attempts to allocate a parallel port at IRQL = DIRQL. The system-supplied function driver for parallel ports supplies this routine. |
| [PPARALLEL_TRY_SELECT_ROUTINE callback](..\parallel\nc-parallel-pparallel_try_select_routine.md) | The PPARALLEL_TRY_SELECT_ROUTINE-typed callback routine selects an IEEE 1284.3 daisy chain device or an IEEE 1284 end-of-chain device that is attached to a parallel port. The system-supplied function driver for parallel ports supplies this routine. |
| [PPARALLEL_WRITE callback](..\parallel\nc-parallel-pparallel_write.md) | The PPARALLEL_WRITE-typed callback routine writes data to a parallel device. The system-supplied bus driver for parallel ports supplies this routine. |
| [PTERMINATE_IEEE_MODE callback](..\parallel\nc-parallel-pterminate_ieee_mode.md) | The PTERMINATE_IEEE_MODE-typed callback routine terminates the current IEEE operating mode and sets the mode to IEEE 1284-compatible. The system-supplied bus driver for parallel ports supplies this routine. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_MORE_PARALLEL_PORT_INFORMATION structure](..\parallel\ns-parallel-_more_parallel_port_information.md) | The MORE_PARALLEL_PORT_INFORMATION structure specifies information about the system interface that supports the operation of a parallel port. |
| [_PARALLEL_1284_COMMAND structure](..\parallel\ns-parallel-_parallel_1284_command.md) | The PARALLEL_1284_COMMAND structure specifies information that a client uses to select and deselect an IEEE 1284.3 daisy-chain device or an IEEE 1284 end-of-chain device. |
| [_PARALLEL_CHIP_MODE structure](..\parallel\ns-parallel-_parallel_chip_mode.md) | The PARALLEL_CHIP_MODE structure specifies the operating mode of a parallel port. |
| [_PARALLEL_INTERRUPT_INFORMATION structure](..\parallel\ns-parallel-_parallel_interrupt_information.md) | The PARALLEL_INTERRUPT_INFORMATION structure specifies information that a kernel-mode driver can use in the context of an ISR that the driver connects to a parallel port. |
| [_PARALLEL_INTERRUPT_SERVICE_ROUTINE structure](..\parallel\ns-parallel-_parallel_interrupt_service_routine.md) | The PARALLEL_INTERRUPT_SERVICE_ROUTINE structure specifies interrupt services that a kernel-mode driver can connect to the operation of a parallel port. |
| [_PARALLEL_PNP_INFORMATION structure](..\parallel\ns-parallel-_parallel_pnp_information.md) | The PARALLEL_PNP_INFORMATION structure specifies information about the capabilities of a parallel port. |
| [_PARALLEL_PORT_INFORMATION structure](..\parallel\ns-parallel-_parallel_port_information.md) | The PARALLEL_PORT_INFORMATION structure specifies information about the resources assigned to a parallel port, the capabilities of the parallel port, and pointers to callback routines that a kernel-mode driver can use to operate the parallel port. |
| [_PARCLASS_INFORMATION structure](..\parallel\ns-parallel-_parclass_information.md) | The PARCLASS_INFORMATION structure specifies information about a parallel port, pointers to callback routines to operate a parallel port, and pointers to callback routines to read and write to a parallel device. |
| [_PARCLASS_NEGOTIATION_MASK structure](..\ntddpar\ns-ntddpar-_parclass_negotiation_mask.md) | The PARCLASS_NEGOTIATION_MASK structure specifies the read and write protocols that a driver selects for a parallel device. |
| [_PAR_DEVICE_ID_SIZE_INFORMATION structure](..\ntddpar\ns-ntddpar-_par_device_id_size_information.md) | The PAR_DEVICE_ID_SIZE_INFORMATION structure specifies the size, in bytes, of a buffer that can hold the IEEE 1284 device ID of a parallel device and a NULL terminator. |
| [_PAR_QUERY_INFORMATION structure](..\ntddpar\ns-ntddpar-_par_query_information.md) | The PAR_QUERY_INFORMATION structure specifies the operating status of a parallel port. |
| [_PAR_SET_INFORMATION structure](..\ntddpar\ns-ntddpar-_par_set_information.md) | The PAR_SET_INFORMATION structure specifies the initial operating status of a parallel port. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_IEEE1284_GET_MODE IOCTL](..\ntddpar\ni-ntddpar-ioctl_ieee1284_get_mode.md) | The IOCTL_IEEE1284_GET_MODE request returns the IEEE 1284 read and write protocols that are currently set for a parallel device. |
| [IOCTL_IEEE1284_NEGOTIATE IOCTL](..\ntddpar\ni-ntddpar-ioctl_ieee1284_negotiate.md) | The IOCTL_IEEE1284_NEGOTIATE request sets the read and write protocols that are used for a parallel device. |
| [IOCTL_INTERNAL_DESELECT_DEVICE IOCTL](..\parallel\ni-parallel-ioctl_internal_deselect_device.md) | The IOCTL_INTERNAL_DESELECT_DEVICE request deselects an IEEE 1284.3 daisy-chain device or an IEEE 1284 end-of-chain device attached to a parallel port. |
| [IOCTL_INTERNAL_DISCONNECT_IDLE IOCTL](..\parallel\ni-parallel-ioctl_internal_disconnect_idle.md) | The IOCTL_INTERNAL_DISCONNECT_IDLE request disconnects the IEEE 1284 operating modes that are set for a parallel device. |
| [IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO IOCTL](..\parallel\ni-parallel-ioctl_internal_get_more_parallel_port_info.md) | The IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO request returns information about a parallel port. |
| [IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO IOCTL](..\parallel\ni-parallel-ioctl_internal_get_parallel_pnp_info.md) | The IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO request returns Plug and Play information about a parallel port. |
| [IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO IOCTL](..\parallel\ni-parallel-ioctl_internal_get_parallel_port_info.md) | The IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO request returns information about a parallel port. |
| [IOCTL_INTERNAL_INIT_1284_3_BUS IOCTL](..\parallel\ni-parallel-ioctl_internal_init_1284_3_bus.md) | The IOCTL_INTERNAL_INIT_1284_3_BUS request initializes and assigns an IEEE 1284.3 device ID to all the 1284.3 daisy chain devices that are attached to a parallel port. |
| [IOCTL_INTERNAL_LOCK_PORT IOCTL](..\parallel\ni-parallel-ioctl_internal_lock_port.md) | The IOCTL_INTERNAL_LOCK_PORT request allocates the parallel device's parent parallel port and selects the parallel device on the port. |
| [IOCTL_INTERNAL_LOCK_PORT_NO_SELECT IOCTL](..\parallel\ni-parallel-ioctl_internal_lock_port_no_select.md) | The IOCTL_INTERNAL_LOCK_PORT_NO_SELECT request allocates the parallel device's parent parallel port, but does not select the parallel device. |
| [IOCTL_INTERNAL_PARALLEL_CLEAR_CHIP_MODE IOCTL](..\parallel\ni-parallel-ioctl_internal_parallel_clear_chip_mode.md) | The IOCTL_INTERNAL_PARALLEL_CLEAR_CHIP_MODE request clears the operating mode of a parallel port. |
| [IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT IOCTL](..\parallel\ni-parallel-ioctl_internal_parallel_connect_interrupt.md) | The IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT request connects an optional interrupt service routine and an optional deferred port check routine to a parallel port. |
| [IOCTL_INTERNAL_PARALLEL_DISCONNECT_INTERRUPT IOCTL](..\parallel\ni-parallel-ioctl_internal_parallel_disconnect_interrupt.md) | The IOCTL_INTERNAL_PARALLEL_DISCONNECT_INTERRUPT request disconnects an interrupt service routine (and an optional deferred port check service routine) that was connected by using an IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT request. |
| [IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE IOCTL](..\parallel\ni-parallel-ioctl_internal_parallel_port_allocate.md) | The IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE request allocates a parallel port for exclusive access by a client. |
| [IOCTL_INTERNAL_PARALLEL_PORT_FREE IOCTL](..\parallel\ni-parallel-ioctl_internal_parallel_port_free.md) | The IOCTL_INTERNAL_PARALLEL_PORT_FREE request frees a parallel port. |
| [IOCTL_INTERNAL_PARALLEL_SET_CHIP_MODE IOCTL](..\parallel\ni-parallel-ioctl_internal_parallel_set_chip_mode.md) | The IOCTL_INTERNAL_PARALLEL_SET_CHIP_MODE request sets the operating mode of a parallel port. |
| [IOCTL_INTERNAL_PARCLASS_CONNECT IOCTL](..\parallel\ni-parallel-ioctl_internal_parclass_connect.md) | The IOCTL_INTERNAL_PARCLASS_CONNECT request returns information about a parallel port and the callback routines that the system-supplied bus driver for parallel ports provides to operate the parallel port. |
| [IOCTL_INTERNAL_PARCLASS_DISCONNECT IOCTL](..\parallel\ni-parallel-ioctl_internal_parclass_disconnect.md) | The IOCTL_INTERNAL_PARCLASS_DISCONNECT request disconnects a client from a parallel device. |
| [IOCTL_INTERNAL_RELEASE_PARALLEL_PORT_INFO IOCTL](..\parallel\ni-parallel-ioctl_internal_release_parallel_port_info.md) | The IOCTL_INTERNAL_RELEASE_PARALLEL_PORT_INFO request returns STATUS_SUCCESS. |
| [IOCTL_INTERNAL_SELECT_DEVICE IOCTL](..\parallel\ni-parallel-ioctl_internal_select_device.md) | The IOCTL_INTERNAL_SELECT_DEVICE request |
| [IOCTL_INTERNAL_UNLOCK_PORT IOCTL](..\parallel\ni-parallel-ioctl_internal_unlock_port.md) | The IOCTL_INTERNAL_UNLOCK_PORT request deselects a parallel device and frees the parallel device's parent parallel port. |
| [IOCTL_INTERNAL_UNLOCK_PORT_NO_DESELECT IOCTL](..\parallel\ni-parallel-ioctl_internal_unlock_port_no_deselect.md) | The IOCTL_INTERNAL_UNLOCK_PORT_NO_DESELECT request frees a parallel device's parent parallel port. |
| [IOCTL_PAR_GET_DEFAULT_MODES IOCTL](..\ntddpar\ni-ntddpar-ioctl_par_get_default_modes.md) | The IOCTL_PAR_GET_DEFAULT_MODES request returns the default write (forward) and read (reverse) IEEE 1284 protocols that the system-supplied bus driver for parallel ports uses. |
| [IOCTL_PAR_GET_DEVICE_CAPS IOCTL](..\ntddpar\ni-ntddpar-ioctl_par_get_device_caps.md) | The IOCTL_PAR_GET_DEVICE_CAPS request does the following |
| [IOCTL_PAR_IS_PORT_FREE IOCTL](..\ntddpar\ni-ntddpar-ioctl_par_is_port_free.md) | The IOCTL_PAR_IS_PORT_FREE request determines if a parallel device's parent parallel port is free at the time the system-supplied bus driver for parallel ports processes the request. |
| [IOCTL_PAR_QUERY_DEVICE_ID IOCTL](..\ntddpar\ni-ntddpar-ioctl_par_query_device_id.md) | The IOCTL_PAR_QUERY_DEVICE_ID request returns the IEEE 1284 device ID of a parallel device assigned by the system-supplied function driver for parallel ports. |
| [IOCTL_PAR_QUERY_DEVICE_ID_SIZE IOCTL](..\ntddpar\ni-ntddpar-ioctl_par_query_device_id_size.md) | The IOCTL_PAR_QUERY_DEVICE_ID_SIZE request returns the size, in bytes, of a buffer that can hold a device's IEEE 1284 device ID and a NULL terminator. |
| [IOCTL_PAR_QUERY_INFORMATION IOCTL](..\ntddpar\ni-ntddpar-ioctl_par_query_information.md) | The IOCTL_PAR_QUERY_INFORMATION request returns the status of an IEEE 1284 end-of-chain device. |
| [IOCTL_PAR_QUERY_LOCATION IOCTL](..\ntddpar\ni-ntddpar-ioctl_par_query_location.md) | The IOCTL_PAR_QUERY_LOCATION request returns the &#0034;LPTn&#0034; or &#0034;LPTn.m&#0034; symbolic link name associated with a parallel device. |
| [IOCTL_PAR_QUERY_RAW_DEVICE_ID IOCTL](..\ntddpar\ni-ntddpar-ioctl_par_query_raw_device_id.md) | The IOCTL_PAR_QUERY_RAW_DEVICE_ID request returns a raw device ID, which includes the following |
| [IOCTL_PAR_SET_INFORMATION IOCTL](..\ntddpar\ni-ntddpar-ioctl_par_set_information.md) | The IOCTL_PAR_SET_INFORMATION request resets and initializes a parallel device. |
| [IOCTL_PAR_SET_READ_ADDRESS IOCTL](..\ntddpar\ni-ntddpar-ioctl_par_set_read_address.md) | The IOCTL_PAR_SET_READ_ADDRESS request sets an extended capabilities port (ECP) or enhanced parallel port (EPP) read address (channel) for a parallel device. |
| [IOCTL_PAR_SET_WRITE_ADDRESS IOCTL](..\ntddpar\ni-ntddpar-ioctl_par_set_write_address.md) | The IOCTL_PAR_SET_WRITE_ADDRESS request sets an extended capabilities port (ECP) or enhanced parallel port (EPP) write address (channel) for a parallel device. The parallel port bus driver queues this request on a work queue for the parallel device. |
