---
UID: NF:ksproxy.KsOpenDefaultDevice
title: KsOpenDefaultDevice function
author: windows-driver-content
description: The KsOpenDefaultDevice function opens a handle to the first device that is listed in the specified Plug and Play (PnP) category.
old-location: stream\ksopendefaultdevice.htm
old-project: stream
ms.assetid: a017f0b7-8f4f-4797-96de-10137cb3443e
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ksproxy_9c80d462-baaa-497b-a337-5d42e94b9c3f.xml, KsOpenDefaultDevice function [Streaming Media Devices], stream.ksopendefaultdevice, KsOpenDefaultDevice, ksproxy/KsOpenDefaultDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Desktop
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
req.lib: Ksproxy.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ksproxy.lib
-	Ksproxy.dll
apiname:
-	KsOpenDefaultDevice
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# KsOpenDefaultDevice function


## -description


The <b>KsOpenDefaultDevice</b> function opens a handle to the first device that is listed in the specified Plug and Play (PnP) category. 


## -syntax


````
HRESULT KsOpenDefaultDevice(
  _In_  REFGUID     Category,
  _In_  ACCESS_MASK Access,
  _Out_ PHANDLE     DeviceHandle
);
````


## -parameters




### -param Category [in]

Identifier of the PnP category to enumerate.


### -param Access [in]

An ACCESS_MASK bitmask specifying how to access the default device.


### -param DeviceHandle [out]

Pointer to a variable that receives the handle to the default device that is opened.


## -returns



Returns NOERROR if successful; otherwise, returns an error code.




## -remarks



The <b>KsOpenDefaultDevice</b> function passes a pointer to <i>Category</i> in a call to the <b>SetupDiGetClassDevs</b> function to obtain a handle to the list of PnP devices. For more information about the ACCESS_MASK bitmask and <b>SetupDiGetClassDevs</b>, see the Microsoft Windows SDK documentation.



