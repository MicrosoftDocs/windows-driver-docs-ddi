---
UID: NF:netadapter.NetAdapterGetPowerSettings
title: NetAdapterGetPowerSettings function
author: windows-driver-content
description: Retrieves the NETPOWERSETTINGS object that is associated with a net adapter.
ms.assetid: e3f3d00f-37f6-4d3c-b170-0d423574ccbd
ms.author: windowsdriverdev
ms.date: 02/06/2018
ms.topic: function
ms.keywords: NetAdapterGetPowerSettings
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.lib: NetAdapterCxStub.lib
req.dll:
req.irql: "<= DISPATCH LEVEL"
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
req.alt-api:
req.alt-loc:
req.typenames: NetAdapterGetPowerSettings
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapter.h
apiname: 
-	NetAdapterGetPowerSettings
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# NetAdapterGetPowerSettings function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Retrieves the NETPOWERSETTINGS object that is associated with a net adapter.

## -parameters

### -param Adapter
The network adapter object that the client created in a prior call to [NetAdapterCreate](nf-netadapter-netadaptercreate.md).

## -returns
Returns the NETPOWERSETTINGS for the specified net adapter object.

## -remarks
The minimum NetAdapterCx version for **NetAdapterGetPowerSettings** is 1.0.

## -see-also

[NetPowerSettingsGetEnabledWakePatternFlags](../netpowersettings/nf-netpowersettings-netpowersettingsgetenabledwakepatternflags.md) 

[NetPowerSettingsGetEnabledProtocolOffloadFlags](../netpowersettings/nf-netpowersettings-netpowersettingsgetenabledprotocoloffloadflags.md) 

[NetPowerSettingsGetEnabledWakeUpFlags](../netpowersettings/nf-netpowersettings-netpowersettingsgetenabledwakeupflags.md)