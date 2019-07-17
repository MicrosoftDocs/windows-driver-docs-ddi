---
UID: NF:poscx.PosCxOpen
title: PosCxOpen function (poscx.h)
description: PosCxOpen is called to create an open PosCx library instance. This function initializes all resources it needs to manage a single open instance. It should be called from the driver's EVT_WDF_DEVICE_FILE_CREATE callback.
old-location: pos\poscxopen.htm
tech.root: pos
ms.assetid: 6AB1BB0A-B350-44D7-B0D0-9A19FD6DEE19
ms.date: 02/23/2018
ms.keywords: PosCxOpen, PosCxOpen function, pos.poscxopen, poscx/PosCxOpen
ms.topic: function
f1_keywords:
 - "poscx/PosCxOpen"
req.header: poscx.h
req.include-header: Poscx.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- poscx.h
api_name:
- PosCxOpen
product:
- Windows
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# PosCxOpen function


## -description


PosCxOpen is called to create an open PosCx library instance. This function initializes all resources it needs to manage a single open instance. It should be called from the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_file_create">EVT_WDF_DEVICE_FILE_CREATE</a>   callback.


## -parameters




### -param device [in]

A handle to a framework device object that represents the device.


### -param fileObject [in]

A handle to a framework file object that identifies the caller associated with the open instance.


### -param deviceInterfaceTag [in]

An identifier used to specify the caller's device interface in a multi-function device.  For a single-interface device, this value should be 0.


## -returns



An appropriate NTSTATUS error code that indicates the open instance completion status.



