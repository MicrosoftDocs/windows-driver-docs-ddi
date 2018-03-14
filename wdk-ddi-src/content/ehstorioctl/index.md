---
UID: NA:ehstorioctl
ms.assetid: a7992c39-d4a1-309f-bf0a-231350d779cf
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ehstorioctl.h header



This header is used by Storage. For more information, see
- [Storage](../_storage/index.md)

Ehstorioctl.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_ENUM_PDO_ENTRY structure](ns-ehstorioctl-_enum_pdo_entry.md) | This structure describes a single entry in a result set of Physical Device Objects (PDOs) that are enumerated with IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS. |
| [_ENUM_PDO_RESULTS structure](ns-ehstorioctl-_enum_pdo_results.md) | This structure describes a result set of Physical Device Objects (PDOs) that are enumerated with IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS. |
| [_LBA_FILTER_TABLE structure](ns-ehstorioctl-_lba_filter_table.md) | The LBA_FILTER_TABLE structure contains the LBA ranges whose access is controlled by a silo driver. |
| [_LBA_FILTER_TABLE_ENTRY structure](ns-ehstorioctl-_lba_filter_table_entry.md) | The LBA_FILTER_TABLE_ENTRY structure contains an individual LBA range for the LBA_FILTER_TABLE sent in an IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE request. |
| [_SILO_DRIVER_CAPABILITIES structure](ns-ehstorioctl-_silo_driver_capabilities.md) | This structure is used to specify the capabilities and support for IOCTL redirection of a storage silo driver. SILO_DRIVER_CAPABILITIES is included in the system buffer of an IOCTL_EHSTOR_DRIVER_REPORT_CAPABILITIES request. |
| [tagACT_AUTHZ_STATE structure](ns-ehstorioctl-tagact_authz_state.md) | This structure describes the Addressable Command Target (ACT) authorization state. |
| [tagSILO_COMMAND structure](ns-ehstorioctl-tagsilo_command.md) | This structure describes a storage silo driver command. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS IOCTL](ni-ehstorioctl-ioctl_ehstor_device_enumerate_pdos.md) | This IOCTL returns a result set containing the enumeration of all active storage Physical Device Objects (PDOs) associated with the given Addressable Command Target (ACT). |
| [IOCTL_EHSTOR_DEVICE_GET_AUTHZ_STATE IOCTL](ni-ehstorioctl-ioctl_ehstor_device_get_authz_state.md) | This IOCTL is used to inform the owning driver for the IEEE 1667 device PDOs that the authorization state has changed. |
| [IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE IOCTL](ni-ehstorioctl-ioctl_ehstor_device_get_queue_state.md) | The IOCTL_EHSTOR_DEVICE_GET_QUEUE_STATE request is sent by silo drivers and applications to determine the state of a storage device queue. |
| [IOCTL_EHSTOR_DEVICE_QUERY_PROPERTIES IOCTL](ni-ehstorioctl-ioctl_ehstor_device_query_properties.md) | A silo driver sends this IOCTL to the storage device stack to query for storage device properties. The Enhanced Storage Class Driver (EHSTOR) will handle the request and return the available properties. |
| [IOCTL_EHSTOR_DEVICE_SET_AUTHZ_STATE IOCTL](ni-ehstorioctl-ioctl_ehstor_device_set_authz_state.md) | This IOCTL is used to inform the owning driver for the IEEE 1667 device PDOs that the authorization state has changed. |
| [IOCTL_EHSTOR_DEVICE_SET_QUEUE_STATE IOCTL](ni-ehstorioctl-ioctl_ehstor_device_set_queue_state.md) | The IOCTL_EHSTOR_DEVICE_SET_QUEUE_STATE request is sent by silo drivers and applications to change the state of a storage device queue. IO requests in the storage device queue are held when the device is temporarily unauthorized. |
| [IOCTL_EHSTOR_DEVICE_SILO_COMMAND IOCTL](ni-ehstorioctl-ioctl_ehstor_device_silo_command.md) | This IOCTL issues a silo command to the targeted silo on the device. Both input and output data are structured according to the definition of silo commands, as found in the IEEE 1667 specification document. |
| [IOCTL_EHSTOR_DRIVER_PERFORM_AUTHZ IOCTL](ni-ehstorioctl-ioctl_ehstor_driver_perform_authz.md) | IOCTL_EHSTOR_DRIVER_PERFORM_AUTHZ is sent by the Enhanced Storage Class Driver (EHSTOR) to the silo driver to initiate on-demand authentication or deauthentication. |
| [IOCTL_EHSTOR_DRIVER_REPORT_CAPABILITIES IOCTL](ni-ehstorioctl-ioctl_ehstor_driver_report_capabilities.md) | This IOCTL is used to inform the enhanced storage (EHSTOR) class driver of the silo driver's capabilities. |
| [IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE IOCTL](ni-ehstorioctl-ioctl_ehstor_driver_update_lba_filter_table.md) | This IOCTL is used to inform the enhanced storage (EHSTOR) class driver of changes to the LBA filter table. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_PDO_CAPS enumeration](ne-ehstorioctl-_pdo_caps.md) | This enumeration describes the capabilities of Physical Device Objects (PDOs). |
| [_PDO_STATE enumeration](ne-ehstorioctl-_pdo_state.md) | This enumeration describes the states of Physical Device Objects (PDOs). |
| [_PDO_TYPE enumeration](ne-ehstorioctl-_pdo_type.md) | This enumeration describes the types of Physical Device Objects (PDOs). |
