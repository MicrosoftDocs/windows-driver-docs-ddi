---
UID: NF:ks.KsSynchronousIoControlDevice
title: KsSynchronousIoControlDevice function
author: windows-driver-content
description: The KsSynchronousIoControlDevice function performs a synchronous device I/O control on the target device object. It waits in a nonalertable state until the I/O completes. This function can only be called at PASSIVE_LEVEL.
old-location: stream\kssynchronousiocontroldevice.htm
old-project: stream
ms.assetid: 7e4ca8ea-52c1-462e-bf02-cc82e9ab2be2
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsSynchronousIoControlDevice
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
req.alt-api: KsSynchronousIoControlDevice
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

# KsSynchronousIoControlDevice function



## -description
The <b>KsSynchronousIoControlDevice</b> function performs a synchronous device I/O control on the target device object. It waits in a nonalertable state until the I/O completes. This function can only be called at PASSIVE_LEVEL.



## -syntax

````
NTSTATUS KsSynchronousIoControlDevice(
  _In_  PFILE_OBJECT    FileObject,
  _In_  KPROCESSOR_MODE RequesorMode,
  _In_  ULONG           IoControl,
  _In_  PVOID           InBuffer,
  _In_  ULONG           InSize,
  _Out_ PVOID           OutBuffer,
  _In_  ULONG           OutSize,
  _Out_ PULONG          BytesReturned
);
````


## -parameters

### -param FileObject [in]

Indicates the file object to fill in the first stack location with.


### -param RequesorMode [in]

Indicates the processor mode to place in the IRP if one needs to be generated.


### -param IoControl [in]

Specifies the I/O control to send.


### -param InBuffer [in]

Points to the device input buffer.


### -param InSize [in]

Specifies the size in bytes of the device input buffer.


### -param OutBuffer [out]

Points to the device output buffer.


### -param OutSize [in]

Specifies the size in bytes of the device output buffer.


### -param BytesReturned [out]

Points to the place in which to put the number of bytes returned.


## -returns
<b>KsSynchronousIoControlDevice </b>returns the result of the device I/O control.


## -remarks
