---
UID: NF:storport.StorPortHardwareReset
title: StorPortHardwareReset function
author: windows-driver-content
description: A miniport can call StorPortHardwareReset to issue a hardware reset.
tech.root: storage
ms.assetid: 99e1fcdc-a727-4198-b02e-f4906f7b3d69
ms.author: windowsdriverdev
ms.date: 12/15/2019
ms.topic: function
ms.keywords: StorPortHardwareReset
req.header: storport.h
f1_keywords:
 - "storport/StorPortHardwareReset"
req.include-header:
req.target-type:
req.target-min-winverclnt: The next version of Windows 10
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- 
api_location: 
- 
api_name: 
- StorPortHardwareReset
product: 
- Windows
targetos: Windows

---

# StorPortHardwareReset function

## -description

A storage miniport can call **StorPortHardwareReset** to issue a hardware reset.

## -parameters

### -param HwDeviceExtension

Pointer to the miniport's device extension.

### -param Type

A [STOR_DEVICE_RESET_TYPE](ne-storport-stor_device_reset_type.md) enum that specifies the type of reset to be issued. Currently, *Type* must be set to **StorFunctionLevelReset**.

## -returns

<!-- ?????????????????????????? -->

## -remarks

<!-- ?????????????????????????? -->

## -see-also

[STOR_DEVICE_RESET_TYPE](ne-storport-stor_device_reset_type.md)
