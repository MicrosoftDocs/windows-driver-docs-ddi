---
UID: NF:ks.KsDefaultDeviceIoCompletion
title: KsDefaultDeviceIoCompletion function
author: windows-driver-content
description: The KsDefaultDeviceIoCompletion function is used to return a default response and to complete any device I/O control.
old-location: stream\ksdefaultdeviceiocompletion.htm
old-project: stream
ms.assetid: 6e466815-aef4-4602-b3cf-66b47b2e3f3b
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.ksdefaultdeviceiocompletion, KsDefaultDeviceIoCompletion function [Streaming Media Devices], ksfunc_ae9df7be-800d-4f4a-a8d9-f39e09653e98.xml, ks/KsDefaultDeviceIoCompletion, KsDefaultDeviceIoCompletion
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsDefaultDeviceIoCompletion
product: Windows
targetos: Windows
req.typenames: 
---

# KsDefaultDeviceIoCompletion function


## -description


The <b>KsDefaultDeviceIoCompletion</b> function is used to return a default response and to complete any device I/O control. It can be used in the KSDISPATCH_TABLE and as the default response to unknown Ioctl's. It is important to use this function so that queries such as property requests return the correct value rather than just STATUS_INVALID_DEVICE_REQUEST when properties are not support for instance.


## -syntax


````
NTSTATUS KsDefaultDeviceIoCompletion(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ PIRP           Irp
);
````


## -parameters




### -param DeviceObject [in]

Specifies the device object dispatched to.


### -param Irp [in]

Specifies the IRP to return a default response to.


## -returns


The <b>KsDefaultDeviceIoCompletion</b> function returns the default response to the possible IOCTLs.



## -remarks


Note that this routine will complete the IRP.


