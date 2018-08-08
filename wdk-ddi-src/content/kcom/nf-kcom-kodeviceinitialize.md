---
UID: NF:kcom.KoDeviceInitialize
title: KoDeviceInitialize function
author: windows-driver-content
description: The KoDeviceInitialize function adds a kernel COM create-item entry to the specified device object.
old-location: stream\kodeviceinitialize.htm
tech.root: stream
ms.assetid: 68ae87c5-7d71-4e85-8052-4e5c422340fb
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: KoDeviceInitialize, KoDeviceInitialize function [Streaming Media Devices], kcom/KoDeviceInitialize, ksfunc_1d3ad49e-d34c-4341-ab30-45c8e96e8b3e.xml, stream.kodeviceinitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: kcom.h
req.include-header: Kcom.h
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
-	KoDeviceInitialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# KoDeviceInitialize function


## -description


<i>This function is intended for internal use only.</i>

The <b>KoDeviceInitialize</b> function adds a kernel COM create-item entry to the specified device object. 


## -parameters




### -param DeviceObject [in]

Pointer to a device object. The device object is assumed to contain a KSOBJECT_HEADER in its device extension.


## -returns



Returns STATUS_SUCCESS if successful. Otherwise, it returns a memory allocation error.



