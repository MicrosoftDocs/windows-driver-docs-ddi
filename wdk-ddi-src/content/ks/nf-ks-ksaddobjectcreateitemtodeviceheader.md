---
UID: NF:ks.KsAddObjectCreateItemToDeviceHeader
title: KsAddObjectCreateItemToDeviceHeader function
author: windows-driver-content
description: The KsAddObjectCreateItemToDeviceHeader function adds the specified create-item to an empty item in the previously allocated create item list for this device header.
old-location: stream\ksaddobjectcreateitemtodeviceheader.htm
tech.root: stream
ms.assetid: cf508b5c-4af8-4371-b833-eaa71535afc5
ms.date: 4/23/2018
ms.keywords: KsAddObjectCreateItemToDeviceHeader, KsAddObjectCreateItemToDeviceHeader function [Streaming Media Devices], ks/KsAddObjectCreateItemToDeviceHeader, ksfunc_89d7ee34-62de-4702-9cfa-5e3b6c9a9819.xml, stream.ksaddobjectcreateitemtodeviceheader
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
-	KsAddObjectCreateItemToDeviceHeader
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsAddObjectCreateItemToDeviceHeader function


## -description


The <b>KsAddObjectCreateItemToDeviceHeader</b> function adds the specified create-item to an empty item in the previously allocated create item list for this device header. An empty item is signified by a <b>NULL</b> create dispatch function in the entry. This function assumes that the caller is serializing multiple changes to the create items list.


## -parameters




### -param Header [in]

Points to the device header that contains the previously allocated child create table.


### -param Create [in]

Specifies the create dispatch function.


### -param Context [in]

Specifies the context parameter.


### -param ObjectClass [in]

Specifies a pointer to a <b>NULL</b>-terminated character string that will be used for comparison on create requests. This pointer must remain valid while the device object is active.


### -param SecurityDescriptor [in, optional]

Specifies the security descriptor. This must remain valid while the device object is active. This parameter is optional.


## -returns



The <b>KsAddObjectCreateItemToDeviceHeader</b> function returns STATUS_SUCCESS if an empty create item slot was found and the item was added.If unsuccessful, it returns STATUS_ALLOTTED_SPACE_EXCEEDED.



