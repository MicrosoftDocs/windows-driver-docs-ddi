---
UID: NA:smclib
ms.assetid: 48cd2b63-634e-3de2-8512-b526fb95a434
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Smclib.h header



This header is used by Windows kernel, Smart Card Reader Devices. For more information, see
- [Windows kernel](../_kernel/index.md)
- [Smart Card Reader Devices](../_smartcrd/index.md)

Smclib.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_CLOCK_RATE_CONVERSION structure](ns-smclib-_clock_rate_conversion.md) | The CLOCK_RATE_CONVERSION structure holds a value that determines the duration of a bit of data and the corresponding maximum operating frequency that accompanies the indicated bit length. |
| [_PTS_DATA structure](ns-smclib-_pts_data.md) | The PTS_DATA structure is used for protocol type selection (PTS). |
| [_SCARD_CARD_CAPABILITIES structure](ns-smclib-_scard_card_capabilities.md) | The SCARD_CARD_CAPABILITIES structure declaration defines the data that is stored in the CardCapabilites member of the SMARTCARD_EXTENSION structure and holds all information that is specific to the particular smart card that is currently used. |
| [_SCARD_READER_CAPABILITIES structure](ns-smclib-_scard_reader_capabilities.md) | The SCARD_READER_CAPABILITIES structure holds state information about the smart card reader. |
| [_SMARTCARD_EXTENSION structure](ns-smclib-_smartcard_extension.md) | The SMARTCARD_EXTENSION structure is used by both the smart card reader driver and the smart card driver library to access all other smart card data structures. |
| [_SMARTCARD_REPLY structure](ns-smclib-_smartcard_reply.md) | Describes the reply buffer received from the smart card. |
| [_SMARTCARD_REQUEST structure](ns-smclib-_smartcard_request.md) | Describes the request buffer that contains data to send to the card. |
| [_T0_DATA structure](ns-smclib-_t0_data.md) | The T0_DATA structure is used by the smart card driver library to process T0 I/O. |
| [_T1_DATA structure](ns-smclib-_t1_data.md) | The T1_DATA structure is used by the smart card driver library to process T1 I/O. |
| [_VENDOR_ATTR structure](ns-smclib-_vendor_attr.md) | The VENDOR_ATTR structure defines the data that is stored in the VendorAttr member of the SMARTCARD_EXTENSION structure. VENDOR_ATTR also holds information that identifies the smart card reader, such as the vendor name, unit number, and serial number. |

## Macros

| Title   | Description   |
| ---- |:---- |
| [RtlZeroMemory macro](nf-smclib-rtlzeromemory.md) | The RtlZeroMemory routine fills a block of memory with zeros, given a pointer to the block and the length, in bytes, to be filled. |
