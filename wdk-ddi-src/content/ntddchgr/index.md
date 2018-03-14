---
UID: NA:ntddchgr
ms.assetid: f1bab14a-b109-3e0f-8bfb-f85c148fc4a9
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ntddchgr.h header



This header is used by Storage. For more information, see
- [Storage](../_storage/index.md)

Ntddchgr.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_CHANGER_ELEMENT structure](ns-ntddchgr-_changer_element.md) | The CHANGER_ELEMENT structure contains a description of a changer element. |
| [_CHANGER_ELEMENT_LIST structure](ns-ntddchgr-_changer_element_list.md) | The CHANGER_ELEMENT_LIST structure indicates a range of elements of a single type. |
| [_CHANGER_ELEMENT_STATUS structure](ns-ntddchgr-_changer_element_status.md) | The ChangerGetElementStatus routine returns status information in this structure. |
| [_CHANGER_ELEMENT_STATUS_EX structure](ns-ntddchgr-_changer_element_status_ex.md) | The ChangerGetElementStatus routine returns status information in this structure. |
| [_CHANGER_EXCHANGE_MEDIUM structure](ns-ntddchgr-_changer_exchange_medium.md) | The CHANGER_EXCHANGE_MEDIUM structure is used with the IOCTL_CHANGER_EXCHANGE_MEDIUM request to exchange locations of two pieces of media. |
| [_CHANGER_INITIALIZE_ELEMENT_STATUS structure](ns-ntddchgr-_changer_initialize_element_status.md) | The CHANGER_INITIALIZE_ELEMENT_STATUS structure is used in conjunction with the IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS request to initialize the status of all elements or of a specified number of elements of a particular type. |
| [_CHANGER_MOVE_MEDIUM structure](ns-ntddchgr-_changer_move_medium.md) | The CHANGER_MOVE_MEDIUM structure is used in conjunction with the IOCTL_CHANGER_MOVE_MEDIUM request to move a piece of media from a source element to a destination. |
| [_CHANGER_PRODUCT_DATA structure](ns-ntddchgr-_changer_product_data.md) | The CHANGER_PRODUCT_DATA structure is used in conjunction with the IOCTL_CHANGER_GET_PRODUCT_DATA request to retrieve product data for a device. |
| [_CHANGER_READ_ELEMENT_STATUS structure](ns-ntddchgr-_changer_read_element_status.md) | The CHANGER_READ_ELEMENT_STATUS structure is used in conjunction with the IOCTL_CHANGER_GET_ELEMENT_STATUS request to retrieve the status of all elements or the status of a specified number of elements of a particular type. |
| [_CHANGER_SEND_VOLUME_TAG_INFORMATION structure](ns-ntddchgr-_changer_send_volume_tag_information.md) | This structure is passed to the ChangerQueryVolumeTags routine and is used to specify a search criterion for retrieving changer elements. |
| [_CHANGER_SET_ACCESS structure](ns-ntddchgr-_changer_set_access.md) | The CHANGER_SET_ACCESS structure is used in conjunction with theIOCTL_CHANGER_SET_ACCESS request to set the state of the device's import/export port (IEport), door, or keypad. |
| [_CHANGER_SET_POSITION structure](ns-ntddchgr-_changer_set_position.md) | The CHANGER_SET_POSITION structure is used in conjunction with theIOCTL_CHANGER_SET_POSITION request to set the changer's robotic transport mechanism to the specified element address. |
| [_GET_CHANGER_PARAMETERS structure](ns-ntddchgr-_get_changer_parameters.md) | Retrieves the characteristics of the changer. |
| [_READ_ELEMENT_ADDRESS_INFO structure](ns-ntddchgr-_read_element_address_info.md) | This structure is to retrieve changer elements based on a search criterion specified in a call to the ChangerQueryVolumeTags routine. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_CHANGER_EXCHANGE_MEDIUM IOCTL](ni-ntddchgr-ioctl_changer_exchange_medium.md) | Moves a piece of media from a source element to one destination and the piece of media originally in the first destination to a second destination. The source and second destination are often the same, which essentially swaps the two pieces of media. |
| [IOCTL_CHANGER_GET_ELEMENT_STATUS IOCTL](ni-ntddchgr-ioctl_changer_get_element_status.md) | Returns the status of all elements or the status of a specified number of elements of a particular type. For a description of the possible element types, see CHANGER_ELEMENT. |
| [IOCTL_CHANGER_GET_PARAMETERS IOCTL](ni-ntddchgr-ioctl_changer_get_parameters.md) | Returns the parameters of the device. |
| [IOCTL_CHANGER_GET_PRODUCT_DATA IOCTL](ni-ntddchgr-ioctl_changer_get_product_data.md) | Returns product data for the device. |
| [IOCTL_CHANGER_GET_STATUS IOCTL](ni-ntddchgr-ioctl_changer_get_status.md) | Returns the current status of the device. |
| [IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS IOCTL](ni-ntddchgr-ioctl_changer_initialize_element_status.md) | Initializes the status of all elements or of specified number of elements of a particular type. |
| [IOCTL_CHANGER_MOVE_MEDIUM IOCTL](ni-ntddchgr-ioctl_changer_move_medium.md) | Moves a piece of media from a source element to a destination. |
| [IOCTL_CHANGER_QUERY_VOLUME_TAGS IOCTL](ni-ntddchgr-ioctl_changer_query_volume_tags.md) | Returns volume tag information for the specified elements. |
| [IOCTL_CHANGER_REINITIALIZE_TRANSPORT IOCTL](ni-ntddchgr-ioctl_changer_reinitialize_transport.md) | Physically recalibrates a transport element, typically after the changer has been powered on or a calling application has initiated a recovery operation. Recalibration may involve returning the transport to its &#0034;home&#0034; position. |
| [IOCTL_CHANGER_SET_ACCESS IOCTL](ni-ntddchgr-ioctl_changer_set_access.md) | Sets the state of the device's import/export port (IEport), door, or keypad. |
| [IOCTL_CHANGER_SET_POSITION IOCTL](ni-ntddchgr-ioctl_changer_set_position.md) | Sets the changer's robotic transport mechanism to the specified element address, typically to optimize moving or exchanging media by positioning the transport beforehand. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_CHANGER_DEVICE_PROBLEM_TYPE enumeration](ne-ntddchgr-_changer_device_problem_type.md) | The CHANGER_DEVICE_PROBLEM_TYPE data type contains the values returned by the ChangerPerformDiagnostics routine. |
| [_ELEMENT_TYPE enumeration](ne-ntddchgr-_element_type.md) | The ELEMENT_TYPE enumeration provides a list of changer element types defined by the SCSI-3 specification. |
