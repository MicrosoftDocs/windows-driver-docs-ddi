---
UID: NF:swenum.KsIsBusEnumChildDevice
title: KsIsBusEnumChildDevice function
author: windows-driver-content
description: The KsIsBusEnumChildDevice function determines if the given device object is a child device of the demand-load bus enumerator object.
old-location: stream\ksisbusenumchilddevice.htm
old-project: stream
ms.assetid: 7b9aa600-dd47-4ef1-acc8-02fb1b4f51ce
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsIsBusEnumChildDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: swenum.h
req.include-header: Swenum.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsIsBusEnumChildDevice
req.alt-loc: Ks.lib,Ks.dll
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
req.typenames: STREAM_TIME_REFERENCE, *PSTREAM_TIME_REFERENCE
req.product: Windows 10 or later.
---

# KsIsBusEnumChildDevice function



## -description
<i>This function is intended for internal use only.</i>

The <b>KsIsBusEnumChildDevice</b> function determines if the given device object is a child device of the demand-load bus enumerator object. 



## -syntax

````
NTSTATUS KsIsBusEnumChildDevice(
  _In_  PDEVICE_OBJECT DeviceObject,
  _Out_ PBOOLEAN       ChildDevice
);
````


## -parameters

### -param DeviceObject [in]

Pointer to a device object.


### -param ChildDevice [out]

Pointer to a BOOLEAN to receive the result. <b>KsIsBusEnumChildDevice</b> sets this to <b>TRUE</b> if the given device object is a child device of the demand-load bus enumerator object, or <b>FALSE</b> otherwise.


## -returns
Returns STATUS_SUCCESS if the given device object's device extension is valid; otherwise, it returns an error code.


## -remarks
