---
UID: NF:ks.KsNullDriverUnload
title: KsNullDriverUnload function (ks.h)
description: The KsNullDriverUnload function is a default function a driver can use when it has no other tasks to do in its unload function, but must still allow the device to be unloaded by its presence.
old-location: stream\ksnulldriverunload.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsNullDriverUnload function"]
ms.keywords: KsNullDriverUnload, KsNullDriverUnload function [Streaming Media Devices], ks/KsNullDriverUnload, ksfunc_449d73af-488d-4c4b-b5cb-f706fd48beab.xml, stream.ksnulldriverunload
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
targetos: Windows
req.typenames: 
f1_keywords:
 - KsNullDriverUnload
 - ks/KsNullDriverUnload
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsNullDriverUnload
---

# KsNullDriverUnload function


## -description

The <b>KsNullDriverUnload</b> function is a default function a driver can use when it has no other tasks to do in its unload function, but must still allow the device to be unloaded by its presence.

## -parameters

### -param DriverObject [in]


Specifies the driver object for this device.

## -returns

None

