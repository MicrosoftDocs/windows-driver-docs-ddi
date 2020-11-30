---
UID: NF:hidport.HidNotifyPresence
title: HidNotifyPresence function
description: The HidNotifyPresence function is reserved for the HID driver internal framework
tech.root: _hid
ms.date: 02/05/2019
keywords: ["HidNotifyPresence function"]
ms.keywords: HidNotifyPresence
req.header: hidport.h
req.include-header: hidport.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP SP1 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: Hid.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
f1_keywords:
 - HidNotifyPresence
 - hidport/HidNotifyPresence
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Hid.lib
 - Hid.dll
api_name:
 - HidNotifyPresence
---

# HidNotifyPresence function


## -description

The **HidNotifyPresence** function is reserved for the HID driver internal framework and is not intended to be used by your code.

## -parameters

### -param DeviceObject

(In, PDEVICE_OBJECT)

### -param IsPresent

(In BOOLEAN)

## -returns

This function returns NTSTATUS.

## -remarks

## -see-also

