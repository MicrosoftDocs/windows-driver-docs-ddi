---
UID: NF:ufxclient.UFX_DEVICE_CALLBACKS_INIT
title: UFX_DEVICE_CALLBACKS_INIT function
author: windows-driver-content
description: The UFX_DEVICE_CALLBACKS_INIT macro initializes the UFX_DEVICE_CALLBACKS structure.
old-location: buses\ufx_device_callbacks_init.htm
tech.root: usbref
ms.assetid: D9E7D359-5FC8-44C8-ACA2-641DEFF17616
ms.date: 5/7/2018
ms.keywords: UFX_DEVICE_CALLBACKS_INIT, UFX_DEVICE_CALLBACKS_INIT function [Buses], buses.ufx_device_callbacks_init, ufxclient/UFX_DEVICE_CALLBACKS_INIT
ms.topic: function
req.header: ufxclient.h
req.include-header: 
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
req.lib: ufxstub.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ufxclient.h
api_name:
-	UFX_DEVICE_CALLBACKS_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# UFX_DEVICE_CALLBACKS_INIT function


## -description


The <b>UFX_DEVICE_CALLBACKS_INIT</b> macro initializes the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187971">UFX_DEVICE_CALLBACKS</a> structure.


## -parameters




### -param Callbacks [out]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187971">UFX_DEVICE_CALLBACKS</a> structure.


## -returns



This function does not return a value.




## -remarks



The <b>UFX_DEVICE_CALLBACKS_INIT</b> macro will set all fields of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187971">UFX_DEVICE_CALLBACKS</a> structure to zero and set the <b>Size</b> field appropriately.

The client driver uses the <b>UFX_DEVICE_CALLBACKS_INIT</b> macro the initialize the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187971">UFX_DEVICE_CALLBACKS</a> structure prior to calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>.



