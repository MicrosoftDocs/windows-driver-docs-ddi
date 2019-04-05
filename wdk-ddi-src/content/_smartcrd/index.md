---
UID: TP:smartcrd
ms.assetid: 1f409c41-e10c-39aa-8408-18629cc1c604
ms.date: 05/09/2018
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
product:
- Windows
---

# Smartcard device drivers

## -description

Overview of the Smartcard device drivers technology.

To develop Smartcard device drivers, you need these headers:

 * [scutil.h](../scutil/index.md)
 * [smcdbg.h](../smcdbg/index.md)
 * [smclib.h](../smclib/index.md)
 * [smcnt.h](../smcnt/index.md)

For the programming guide, see [Smartcard device drivers](https://docs.microsoft.com/windows-hardware/drivers/smartcard).

## Structures

| Title   | Description   |
| ---- |:---- |
| [_CLOCK_RATE_CONVERSION structure](../smclib/ns-smclib-_clock_rate_conversion.md) | The CLOCK_RATE_CONVERSION structure holds a value that determines the duration of a bit of data and the corresponding maximum operating frequency that accompanies the indicated bit length. |
| [_OS_DEP_DATA structure](../smcnt/ns-smcnt-_os_dep_data.md) | The OS_DEP_DATA structure defines the data that is stored in the OsData member of the SMARTCARD_EXTENSION structure, which holds smart card information that is specific to the operating system. |
| [_PTS_DATA structure](../smclib/ns-smclib-_pts_data.md) | The PTS_DATA structure is used for protocol type selection (PTS). |
| [_SCARD_CARD_CAPABILITIES structure](../smclib/ns-smclib-_scard_card_capabilities.md) | The SCARD_CARD_CAPABILITIES structure declaration defines the data that is stored in the CardCapabilites member of the SMARTCARD_EXTENSION structure and holds all information that is specific to the particular smart card that is currently used. |
| [_SCARD_READER_CAPABILITIES structure](../smclib/ns-smclib-_scard_reader_capabilities.md) | The SCARD_READER_CAPABILITIES structure holds state information about the smart card reader. |
| [_SMARTCARD_EXTENSION structure](../smclib/ns-smclib-_smartcard_extension.md) | The SMARTCARD_EXTENSION structure is used by both the smart card reader driver and the smart card driver library to access all other smart card data structures. |
| [_SMARTCARD_REPLY structure](../smclib/ns-smclib-_smartcard_reply.md) | Describes the reply buffer received from the smart card. |
| [_SMARTCARD_REQUEST structure](../smclib/ns-smclib-_smartcard_request.md) | Describes the request buffer that contains data to send to the card. |
| [_T0_DATA structure](../smclib/ns-smclib-_t0_data.md) | The T0_DATA structure is used by the smart card driver library to process T0 I/O. |
| [_T1_DATA structure](../smclib/ns-smclib-_t1_data.md) | The T1_DATA structure is used by the smart card driver library to process T1 I/O. |
| [_VENDOR_ATTR structure](../smclib/ns-smclib-_vendor_attr.md) | The VENDOR_ATTR structure defines the data that is stored in the VendorAttr member of the SMARTCARD_EXTENSION structure. VENDOR_ATTR also holds information that identifies the smart card reader, such as the vendor name, unit number, and serial number. |
