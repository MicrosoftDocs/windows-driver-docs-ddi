---
UID: NA:ntddpar
ms.assetid: a65460d7-ebb7-3fe7-8330-0b5e8be22d0e
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ntddpar.h header



This header is used by Parallel Ports. For more information, see
- [Parallel Ports](../_parports/index.md)

Ntddpar.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_PARCLASS_NEGOTIATION_MASK structure](ns-ntddpar-_parclass_negotiation_mask.md) | The PARCLASS_NEGOTIATION_MASK structure specifies the read and write protocols that a driver selects for a parallel device. |
| [_PAR_DEVICE_ID_SIZE_INFORMATION structure](ns-ntddpar-_par_device_id_size_information.md) | The PAR_DEVICE_ID_SIZE_INFORMATION structure specifies the size, in bytes, of a buffer that can hold the IEEE 1284 device ID of a parallel device and a NULL terminator. |
| [_PAR_QUERY_INFORMATION structure](ns-ntddpar-_par_query_information.md) | The PAR_QUERY_INFORMATION structure specifies the operating status of a parallel port. |
| [_PAR_SET_INFORMATION structure](ns-ntddpar-_par_set_information.md) | The PAR_SET_INFORMATION structure specifies the initial operating status of a parallel port. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_IEEE1284_GET_MODE IOCTL](ni-ntddpar-ioctl_ieee1284_get_mode.md) | The IOCTL_IEEE1284_GET_MODE request returns the IEEE 1284 read and write protocols that are currently set for a parallel device. |
| [IOCTL_IEEE1284_NEGOTIATE IOCTL](ni-ntddpar-ioctl_ieee1284_negotiate.md) | The IOCTL_IEEE1284_NEGOTIATE request sets the read and write protocols that are used for a parallel device. |
| [IOCTL_PAR_GET_DEFAULT_MODES IOCTL](ni-ntddpar-ioctl_par_get_default_modes.md) | The IOCTL_PAR_GET_DEFAULT_MODES request returns the default write (forward) and read (reverse) IEEE 1284 protocols that the system-supplied bus driver for parallel ports uses. |
| [IOCTL_PAR_GET_DEVICE_CAPS IOCTL](ni-ntddpar-ioctl_par_get_device_caps.md) | The IOCTL_PAR_GET_DEVICE_CAPS request does the following |
| [IOCTL_PAR_IS_PORT_FREE IOCTL](ni-ntddpar-ioctl_par_is_port_free.md) | The IOCTL_PAR_IS_PORT_FREE request determines if a parallel device's parent parallel port is free at the time the system-supplied bus driver for parallel ports processes the request. |
| [IOCTL_PAR_QUERY_DEVICE_ID IOCTL](ni-ntddpar-ioctl_par_query_device_id.md) | The IOCTL_PAR_QUERY_DEVICE_ID request returns the IEEE 1284 device ID of a parallel device assigned by the system-supplied function driver for parallel ports. |
| [IOCTL_PAR_QUERY_DEVICE_ID_SIZE IOCTL](ni-ntddpar-ioctl_par_query_device_id_size.md) | The IOCTL_PAR_QUERY_DEVICE_ID_SIZE request returns the size, in bytes, of a buffer that can hold a device's IEEE 1284 device ID and a NULL terminator. |
| [IOCTL_PAR_QUERY_INFORMATION IOCTL](ni-ntddpar-ioctl_par_query_information.md) | The IOCTL_PAR_QUERY_INFORMATION request returns the status of an IEEE 1284 end-of-chain device. |
| [IOCTL_PAR_QUERY_LOCATION IOCTL](ni-ntddpar-ioctl_par_query_location.md) | The IOCTL_PAR_QUERY_LOCATION request returns the &#0034;LPTn&#0034; or &#0034;LPTn.m&#0034; symbolic link name associated with a parallel device. |
| [IOCTL_PAR_QUERY_RAW_DEVICE_ID IOCTL](ni-ntddpar-ioctl_par_query_raw_device_id.md) | The IOCTL_PAR_QUERY_RAW_DEVICE_ID request returns a raw device ID, which includes the following |
| [IOCTL_PAR_SET_INFORMATION IOCTL](ni-ntddpar-ioctl_par_set_information.md) | The IOCTL_PAR_SET_INFORMATION request resets and initializes a parallel device. |
| [IOCTL_PAR_SET_READ_ADDRESS IOCTL](ni-ntddpar-ioctl_par_set_read_address.md) | The IOCTL_PAR_SET_READ_ADDRESS request sets an extended capabilities port (ECP) or enhanced parallel port (EPP) read address (channel) for a parallel device. |
| [IOCTL_PAR_SET_WRITE_ADDRESS IOCTL](ni-ntddpar-ioctl_par_set_write_address.md) | The IOCTL_PAR_SET_WRITE_ADDRESS request sets an extended capabilities port (ECP) or enhanced parallel port (EPP) write address (channel) for a parallel device. The parallel port bus driver queues this request on a work queue for the parallel device. |
