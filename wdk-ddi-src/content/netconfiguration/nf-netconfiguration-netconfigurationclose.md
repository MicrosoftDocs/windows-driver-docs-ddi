---
UID: NF:netconfiguration.NetConfigurationClose
title: NetConfigurationClose function
author: windows-driver-content
description: Releases the handle to the registry key that is associated with an adapter configuration object and then deletes the adapter configuration object.
ms.assetid: 5a133c35-8f4c-4af0-8fc1-82f9ad427f56
ms.author: windowsdriverdev
ms.date: 02/07/2018
ms.topic: function
ms.keywords: NetConfigurationClose
req.header: netconfiguration.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.lib: netadaptercxstub.lib
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
req.alt-api:
req.alt-loc:
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netconfiguration.h
apiname: 
-	NetConfigurationClose
product:
-	Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NetConfigurationClose function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

Releases the handle to the registry key that is associated with an adapter configuration object and then deletes the adapter configuration object.

## -parameters

### -param Configuration
A handle to an adapter configuration object opened in a prior call to [NetAdapterOpenConfiguration](../netadapter/nf-netadapter-netadapteropenconfiguration.md) or [NetConfigurationOpenSubConfiguration](nf-netconfiguration-netconfigurationopensubconfiguration.md).

## -returns
This method does not return a value.

## -remarks
**NetConfigurationClose** is an alias of [WdfObjectDelete](../wdfobject/nf-wdfobject-wdfobjectdelete.md). Because the configuration object, like all NetAdapterCx objects, is a WDF object, you can use [WdfObjectDelete](../wdfobject/nf-wdfobject-wdfobjectdelete.md) interchangeably.



## -see-also

[NetAdapterOpenConfiguration](../netadapter/nf-netadapter-netadapteropenconfiguration.md)

[NetConfigurationOpenSubConfiguration](nf-netconfiguration-netconfigurationopensubconfiguration.md)