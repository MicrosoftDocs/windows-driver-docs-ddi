---
UID: NA:winbio_types
ms.assetid: 628c8ccb-7d9b-34de-a75a-7126646798ee
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Winbio_Types.h header



This header is used by biometric. For more information, see
- [biometric](../_biometric/index.md)

Winbio_Types.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_WINBIO_BIR structure](ns-winbio_types-_winbio_bir.md) | The WINBIO_BIR structure is the root of the BIR (Biometric Information Record). It contains the size and offset of any other data elements in the BIR. |
| [_WINBIO_BIR_DATA structure](ns-winbio_types-_winbio_bir_data.md) | The WINBIO_BIR_DATA structure contains the location and size of a block in a BIR. The offset is measured from the beginning of the WINBIO_BIR structure. |
| [_WINBIO_BIR_HEADER structure](ns-winbio_types-_winbio_bir_header.md) | The WINBIO_BIR_HEADER structure contains the Common Biometric Exchange File Format (CBEFF) Patron Format A information that describes the rest of the BIR. |
| [_WINBIO_REGISTERED_FORMAT structure](ns-winbio_types-_winbio_registered_format.md) | The WINBIO_REGISTERED_FORMAT structure specifies a biometric data format. |
| [_WINBIO_VERSION structure](ns-winbio_types-_winbio_version.md) | The WINBIO_VERSION structure describes major and minor version information for a WBDI driver. |
