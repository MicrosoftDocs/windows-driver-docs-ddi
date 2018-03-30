---
UID: NA:ntddcdvd
ms.assetid: c19577b0-fb08-3e9e-81f8-18bcb91be067
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ntddcdvd.h header



This header is used by Storage. For more information, see
- [Storage](../_storage/index.md)

Ntddcdvd.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [DVD_READ_STRUCTURE structure](ns-ntddcdvd-dvd_read_structure.md) | The DVD_READ_STRUCTURE structure is used in conjunction with the IOCTL_DVD_READ_STRUCTURE request to retrieve a DVD descriptor containing information about a DVD disc. |
| [_AACS_BINDING_NONCE structure](ns-ntddcdvd-_aacs_binding_nonce.md) | The AACS_BINDING_NONCE structure contains the binding nonce. |
| [_AACS_CERTIFICATE structure](ns-ntddcdvd-_aacs_certificate.md) | The AACS_CERTIFICATE structure contains a cryptographically random 160-bit value, followed by a 92-byte certificate. |
| [_AACS_CHALLENGE_KEY structure](ns-ntddcdvd-_aacs_challenge_key.md) | The AACS_CHALLENGE_KEY structure contains the challenge key that the device sends to the host. |
| [_AACS_MEDIA_ID structure](ns-ntddcdvd-_aacs_media_id.md) | The AACS_MEDIA_ID structure contains an Advanced Access Content System (AACS) media identifier and corresponding message authentication code (MAC). |
| [_AACS_READ_BINDING_NONCE structure](ns-ntddcdvd-_aacs_read_binding_nonce.md) | The AACS_READ_BINDING_NONCE structure is a wrapper for the Authentication Grant Identifier (AGID) and logical block address (LBA)/length pair that are required to read a nonce. |
| [_AACS_SEND_CERTIFICATE structure](ns-ntddcdvd-_aacs_send_certificate.md) | The AACS_SEND_CERTIFICATE structure is a wrapper for both an Advanced Access Content System (AACS) certificate and an Authentication Grant Identifier (AGID). |
| [_AACS_SEND_CHALLENGE_KEY structure](ns-ntddcdvd-_aacs_send_challenge_key.md) | The AACS_SEND_CHALLENGE_KEY structure is defined as a challenge key that host software sends to an Advanced Access Content System (AACS) device. |
| [_AACS_SERIAL_NUMBER structure](ns-ntddcdvd-_aacs_serial_number.md) | The AACS_SERIAL_NUMBER structure contains an Advanced Access Content System (AACS) serial number and corresponding message authentication code (MAC). |
| [_AACS_VOLUME_ID structure](ns-ntddcdvd-_aacs_volume_id.md) | The AACS_VOLUME_ID structure contains an Advanced Access Content System (AACS) volume ID and the corresponding message authentication code (MAC). |
| [_DVD_BCA_DESCRIPTOR structure](ns-ntddcdvd-_dvd_bca_descriptor.md) | The DVD_BCA_DESCRIPTOR structure is used in conjunction with the IOCTL_DVD_READ_STRUCTURE request to retrieve a DVD burst cutting area (BCA) descriptor. |
| [_DVD_COPYRIGHT_DESCRIPTOR structure](ns-ntddcdvd-_dvd_copyright_descriptor.md) | The DVD_COPYRIGHT_DESCRIPTOR structure is used in conjunction with the IOCTL_DVD_READ_STRUCTURE request to retrieve a DVD copyright descriptor. |
| [_DVD_COPY_PROTECT_KEY structure](ns-ntddcdvd-_dvd_copy_protect_key.md) | The DVD_COPY_PROTECT_KEY structure is used in conjunction with the IOCTL_DVD_READ_KEY request to execute a report key command of the specified type. |
| [_DVD_DISK_KEY_DESCRIPTOR structure](ns-ntddcdvd-_dvd_disk_key_descriptor.md) | The DVD_DISK_KEY_DESCRIPTOR structure is used in conjunction with the IOCTL_DVD_READ_STRUCTURE request to retrieve a DVD disc key descriptor. |
| [_DVD_LAYER_DESCRIPTOR structure](ns-ntddcdvd-_dvd_layer_descriptor.md) | The DVD_LAYER_DESCRIPTOR structure is used in conjunction with the IOCTL_DVD_READ_STRUCTURE request to retrieve a DVD layer descriptor. |
| [_DVD_MANUFACTURER_DESCRIPTOR structure](ns-ntddcdvd-_dvd_manufacturer_descriptor.md) | The DVD_MANUFACTURER_DESCRIPTOR structure is used in conjunction with the IOCTL_DVD_READ_STRUCTURE request to retrieve a DVD manufacturer descriptor. |
| [_DVD_REGION structure](ns-ntddcdvd-_dvd_region.md) | The DVD_REGION structure is used in conjunction with the IOCTL_DVD_GET_REGION request to retrieve region playback control (RPC) information for a DVD device. |
| [_STORAGE_SET_READ_AHEAD structure](ns-ntddcdvd-_storage_set_read_ahead.md) | The STORAGE_SET_READ_AHEAD structure is used in conjunction with the IOCTL_STORAGE_SET_READ_AHEAD request to instruct the device to skip to the target address upon reaching the trigger address. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_AACS_END_SESSION IOCTL](ni-ntddcdvd-ioctl_aacs_end_session.md) | Releases the Authentication Grant Identifier (AGID) that was obtained by IOCTL_AACS_START_SESSION. |
| [IOCTL_AACS_GENERATE_BINDING_NONCE IOCTL](ni-ntddcdvd-ioctl_aacs_generate_binding_nonce.md) | Reads the Advanced Access Content System (AACS) binding nonce starting at the specified byte offset on the disc, as part of the protocol for writing to a protected data area. |
| [IOCTL_AACS_GET_CERTIFICATE IOCTL](ni-ntddcdvd-ioctl_aacs_get_certificate.md) | Queries the logical unit for the device certificate. |
| [IOCTL_AACS_GET_CHALLENGE_KEY IOCTL](ni-ntddcdvd-ioctl_aacs_get_challenge_key.md) | Queries the logical unit for the device's challenge key. The challenge key consists of a point on an elliptic curve and its associated signature. |
| [IOCTL_AACS_READ_BINDING_NONCE IOCTL](ni-ntddcdvd-ioctl_aacs_read_binding_nonce.md) | Reads the Advanced Access Content System (AACS) binding nonce starting at the specified byte offset on the disc, as part of the protocol for reading a protected data area. |
| [IOCTL_AACS_READ_MEDIA_ID IOCTL](ni-ntddcdvd-ioctl_aacs_read_media_id.md) | Reads the Advanced Access Content System (AACS)-specific media identifier data. |
| [IOCTL_AACS_READ_MEDIA_KEY_BLOCK IOCTL](ni-ntddcdvd-ioctl_aacs_read_media_key_block.md) | Queries the logical unit for the Media Key Block (MKB). |
| [IOCTL_AACS_READ_MEDIA_KEY_BLOCK_SIZE IOCTL](ni-ntddcdvd-ioctl_aacs_read_media_key_block_size.md) | Queries the logical unit for the size of the buffer that is required to hold the Advanced Access Control System (AACS) Media Key Block (MKB). |
| [IOCTL_AACS_READ_SERIAL_NUMBER IOCTL](ni-ntddcdvd-ioctl_aacs_read_serial_number.md) | Reads the Advanced Access Content System (AACS)-specific prerecorded media serial number. |
| [IOCTL_AACS_READ_VOLUME_ID IOCTL](ni-ntddcdvd-ioctl_aacs_read_volume_id.md) | Reads the Advanced Access Content System (AACS)-specific volume identifier. |
| [IOCTL_AACS_SEND_CERTIFICATE IOCTL](ni-ntddcdvd-ioctl_aacs_send_certificate.md) | Sends the host certificate to the logical unit. |
| [IOCTL_AACS_SEND_CHALLENGE_KEY IOCTL](ni-ntddcdvd-ioctl_aacs_send_challenge_key.md) | Sends the host's challenge key to the logical unit. The host's challenge key consists of a point on an elliptic curve and its associated signature. |
| [IOCTL_AACS_START_SESSION IOCTL](ni-ntddcdvd-ioctl_aacs_start_session.md) | Retrieves an Authentication Grant Identifier (AGID) that identifies a secure session. |
| [IOCTL_DVD_END_SESSION IOCTL](ni-ntddcdvd-ioctl_dvd_end_session.md) | Ends a DVD session by invalidating its authentication grant ID (AGID). |
| [IOCTL_DVD_GET_REGION IOCTL](ni-ntddcdvd-ioctl_dvd_get_region.md) | Returns Region Playback Control (RPC) information for a DVD device, such as whether the player supports the RPC2 standard, the current region code of the player, and the remaining number of times the player's region code can be changed by the user. |
| [IOCTL_DVD_READ_KEY IOCTL](ni-ntddcdvd-ioctl_dvd_read_key.md) | Returns a copy-protection key of the specified type |
| [IOCTL_DVD_READ_STRUCTURE IOCTL](ni-ntddcdvd-ioctl_dvd_read_structure.md) | Returns information about a DVD disc, such as a layer descriptor, copyright information, or manufacturer-specific information. |
| [IOCTL_DVD_SEND_KEY IOCTL](ni-ntddcdvd-ioctl_dvd_send_key.md) | Sends the specified key to a DVD device to complete the related step in an authentication sequence.This IOCTL has only read access to the device and cannot send keys that make alterations to the hardware configuration. |
| [IOCTL_DVD_SEND_KEY2 IOCTL](ni-ntddcdvd-ioctl_dvd_send_key2.md) | Sends the specified key to a DVD device -to complete the related step in an authentication sequence. The IOCTL_DVD_SEND_KEY2 request has write access to the device and can send a broader range of key types than IOCTL_DVD_SEND_KEY. |
| [IOCTL_DVD_START_SESSION IOCTL](ni-ntddcdvd-ioctl_dvd_start_session.md) | Returns an authentication grant ID (AGID) as a DVD session ID, which a caller must pass to the device in all subsequent operations in a DVD session. |
| [IOCTL_STORAGE_SET_READ_AHEAD IOCTL](ni-ntddcdvd-ioctl_storage_set_read_ahead.md) | Causes the device to skip to the given target address when the device reaches a certain trigger address during read-ahead caching. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [DVD_KEY_TYPE enumeration](ne-ntddcdvd-dvd_key_type.md) | The DVD_KEY_TYPE enumeration type is used in conjunction with the DVD_COPY_PROTECT_KEY structure to indicate a key to be read, to invalidate an authentication grant ID (AGID), and to request state information or region settings. |
| [DVD_STRUCTURE_FORMAT enumeration](ne-ntddcdvd-dvd_structure_format.md) | The DVD_STRUCTURE_FORMAT enumeration type is used in conjunction with the IOCTL_DVD_READ_STRUCTURE request and the DVD_READ_STRUCTURE structure to retrieve a DVD descriptor. |
