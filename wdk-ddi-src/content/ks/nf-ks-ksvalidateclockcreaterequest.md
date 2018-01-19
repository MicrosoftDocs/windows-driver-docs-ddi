---
UID: NF:ks.KsValidateClockCreateRequest
title: KsValidateClockCreateRequest function
author: windows-driver-content
description: The KsValidateClockCreateRequest function validates the clock creation request and returns the create structure associated with the request.This can only be called at PASSIVE_LEVEL.
old-location: stream\ksvalidateclockcreaterequest.htm
old-project: stream
ms.assetid: ec10c10e-4604-47fc-a2e7-4df9d90acf0b
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsValidateClockCreateRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsValidateClockCreateRequest
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
req.typenames: 
---

# KsValidateClockCreateRequest function



## -description
The <b>KsValidateClockCreateRequest</b> function validates the clock creation request and returns the create structure associated with the request.

This can only be called at PASSIVE_LEVEL.



## -syntax

````
NTSTATUS KsValidateClockCreateRequest(
  _In_  PIRP            lrp,
  _Out_ PKSCLOCK_CREATE *ClockCreate
);
````


## -parameters

### -param lrp [in]

Specifies the IRP with the clock create request being handled.


### -param ClockCreate [out]

Specifies the clock create structure pointer passed to the create request.


## -returns
The <b>KsValidateClockCreateRequest</b> function returns STATUS_SUCCESS if successful, or an error if unsuccessful.


## -remarks
