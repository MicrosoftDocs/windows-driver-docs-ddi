---
UID: NA:61883
ms.assetid: e401eb24-793e-3800-b0b7-55496f44fbb8
ms.author: windowsdriverdev
ms.date: 04/02/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# 61883.h header


## -description


This header is used by ieee. For more information, see:

- [IEEE 1394 bus](../_ieee/index.md)

An IEC-61883 client driver must communicate with its device by submitting IRPs down the device stack to the IEC-61883 protocol driver. 

To use these I/O requests, include the header file 61883.h, which is included in the Microsoft Windows Driver Kit (WDK).

## INIT_61883_HEADER Macro

The INIT_61883_HEADER macro initializes the Function and Version members of an AV_61883_REQUEST structure.

Parameters

Return value

## Related topics

Send comments about this topic to Microsoft

