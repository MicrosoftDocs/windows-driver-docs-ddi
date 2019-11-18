---
UID: NF:mbbcx.MbbDeviceReportWakeReason
title: MbbDeviceReportWakeReason function (mbbcx.h)
author: windows-driver-content
description: The MbbDeviceReportWakeReason method reports to the framework the reason that a mobile broadband device has generated a wake-up event.
tech.root: netvista
ms.assetid: 57af271e-cd06-4749-abd1-89f4d3c7075c
ms.author: windowsdriverdev
ms.date: 11/07/2019
ms.topic: function
f1_keywords:
 - "mbbcx/MbbDeviceReportWakeReason"
ms.keywords: MbbDeviceReportWakeReason
req.header: mbbcx.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: The next version of Windows 10
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib: mbbcxstub.lib
req.dll:
req.irql: PASSIVE_LEVEL
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
- LibDef
api_location: 
- mbbcxstub.lib
api_name: 
- MbbDeviceReportWakeReason
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# MbbDeviceReportWakeReason function


## -description

The **MbbDeviceReportWakeReason** method reports to the framework the reason that a mobile broadband device has generated a wake-up event.

## -parameters

### -param Device

A handle to the WDFDEVICE object.

### -param Reason

A [**MBB_WAKE_REASON_TYPE**](../mbbcx/ne-mbbcx-_mbb_wake_reason_type.md) value that describes the reason for the wake-up event.

## -returns

This method does not return a value.

## -remarks

## -see-also