---
UID: NE:storport._STOR_DEVICE_RESET_TYPE
title: STOR_DEVICE_RESET_TYPE
author: windows-driver-content
description: The STOR_DEVICE_RESET_TYPE enum specifies the type of device reset being requested in a call to StorPortHardwareReset.
tech.root: storage
ms.assetid: b0c412bb-9354-4599-9078-8b8656185d15
ms.author: windowsdriverdev
ms.date: 12/15/2019
ms.topic: enum
ms.keywords: STOR_DEVICE_RESET_TYPE, STOR_DEVICE_RESET_TYPE, 
req.header: storport.h
f1_keywords:
 - "storport/STOR_DEVICE_RESET_TYPE"
req.include-header:
req.target-type:
req.target-min-winverclnt: The next version of Windows 10
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: STOR_DEVICE_RESET_TYPE
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - storport.h
api_name: 
 - STOR_DEVICE_RESET_TYPE
product: 
 - Windows
targetos: Windows
---

# STOR_DEVICE_RESET_TYPE enumeration

## -description

The STOR_DEVICE_RESET_TYPE enum specifies the type of device reset being requested in a call to [**StorPortHardwareReset**](nf-storport-storporthardwarereset.md).

## -enum-fields

### -field StorFunctionLevelReset

The reset operation request is for a function-level device reset. In this case, the reset operation is restricted to a specific device, and is not visible to other devices. The device stays connected to the bus throughout the reset and returns to a valid (initial) state after the reset.

### -field StorPlatformLevelReset

The reset operation request is for a platform-level device reset. In this case, the reset operation causes the device to be reported as missing from the bus. <!-- Should I copy more from this page? https://docs.microsoft.com/windows-hardware/drivers/kernel/resetting-and-recovering-a-device -->

## -remarks

## -see-also

[**StorPortHardwareReset**](nf-storport-storporthardwarereset.md)
