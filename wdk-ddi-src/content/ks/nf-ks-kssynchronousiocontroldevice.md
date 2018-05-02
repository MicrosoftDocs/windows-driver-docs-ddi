---
UID: NF:ks.KsSynchronousIoControlDevice
title: KsSynchronousIoControlDevice function
author: windows-driver-content
description: The KsSynchronousIoControlDevice function performs a synchronous device I/O control on the target device object. It waits in a nonalertable state until the I/O completes. This function can only be called at PASSIVE_LEVEL.
old-location: stream\kssynchronousiocontroldevice.htm
old-project: stream
ms.assetid: 7e4ca8ea-52c1-462e-bf02-cc82e9ab2be2
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: KsSynchronousIoControlDevice, KsSynchronousIoControlDevice function [Streaming Media Devices], ks/KsSynchronousIoControlDevice, ksfunc_b3bba8f7-d9fb-4372-bfff-f39b4d925561.xml, stream.kssynchronousiocontroldevice
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsSynchronousIoControlDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsSynchronousIoControlDevice function


## -description


The <b>KsSynchronousIoControlDevice</b> function performs a synchronous device I/O control on the target device object. It waits in a nonalertable state until the I/O completes. This function can only be called at PASSIVE_LEVEL.


## -parameters




### -param FileObject [in]

Indicates the file object to fill in the first stack location with.


### -param RequestorMode

TBD


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


#### - RequesorMode [in]

Indicates the processor mode to place in the IRP if one needs to be generated.


## -returns



<b>KsSynchronousIoControlDevice </b>returns the result of the device I/O control.



