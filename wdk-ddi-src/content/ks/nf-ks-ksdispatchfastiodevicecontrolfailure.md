---
UID: NF:ks.KsDispatchFastIoDeviceControlFailure
title: KsDispatchFastIoDeviceControlFailure function (ks.h)
description: The KsDispatchFastIoDeviceControlFailure function is used in a KSDISPATCH_TABLE.FastDeviceIoControl entry that are not handled. The function should always return FALSE.
old-location: stream\ksdispatchfastiodevicecontrolfailure.htm
tech.root: stream
ms.assetid: 7fb83c8d-e815-46c6-8011-75b25a4c0dd7
ms.date: 04/23/2018
keywords: ["KsDispatchFastIoDeviceControlFailure function"]
ms.keywords: KsDispatchFastIoDeviceControlFailure, KsDispatchFastIoDeviceControlFailure function [Streaming Media Devices], ks/KsDispatchFastIoDeviceControlFailure, ksfunc_f8510e75-1698-4ce9-acd8-d5db73a7c035.xml, stream.ksdispatchfastiodevicecontrolfailure
f1_keywords:
 - "ks/KsDispatchFastIoDeviceControlFailure"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsDispatchFastIoDeviceControlFailure
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsDispatchFastIoDeviceControlFailure function


## -description


The <b>KsDispatchFastIoDeviceControlFailure</b> function is used in a KSDISPATCH_TABLE.FastDeviceIoControl entry that are not handled. The function should always return <b>FALSE</b>. 


## -parameters




### -param FileObject [in]

Not used.


### -param Wait [in]

Not used.


### -param InputBuffer [in, optional]

Not used.


### -param InputBufferLength [in]

Not used.


### -param OutputBuffer [out, optional]

Not used.


### -param OutputBufferLength [in]

Not used.


### -param IoControlCode [in]

Not used.


### -param IoStatus [out]

Not used.


### -param DeviceObject [in]

Not used.


## -returns



The <b>KsDispatchFastIoDeviceControlFailure</b> function returns <b>FALSE</b>.




## -remarks



The <b>KsDispatchFastIoDeviceControlFailure</b> function is needed since the dispatch table for a particular opened instance of a device may not handle a specific major function that another opened instance needs to handle. Therefore, the function pointer in the driver object must always point to a function, such as the <b>KsDispatchFastIoDeviceControlFailure</b> function, that calls a dispatch table entry.



