---
UID: NF:ks.KsFilterFactorySetDeviceClassesState
title: KsFilterFactorySetDeviceClassesState function (ks.h)
description: The KsFilterFactorySetDeviceClassesState function enables or disables the device classes that have been registered by a given filter factory.
old-location: stream\ksfilterfactorysetdeviceclassesstate.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsFilterFactorySetDeviceClassesState function"]
ms.keywords: KsFilterFactorySetDeviceClassesState, KsFilterFactorySetDeviceClassesState function [Streaming Media Devices], avfunc_a88f0816-e755-450f-b8b7-83dee85171f9.xml, ks/KsFilterFactorySetDeviceClassesState, stream.ksfilterfactorysetdeviceclassesstate
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KsFilterFactorySetDeviceClassesState
 - ks/KsFilterFactorySetDeviceClassesState
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsFilterFactorySetDeviceClassesState
---

# KsFilterFactorySetDeviceClassesState function


## -description

The <b>KsFilterFactorySetDeviceClassesState</b> function enables or disables the device classes that have been registered by a given filter factory.

## -parameters

### -param FilterFactory 

[in]
A pointer to the <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory">KSFILTERFACTORY</a> for which to change device class status.

### -param NewState 

[in]
If set to <b>TRUE</b>, the device classes are enabled; if <b>FALSE</b>, they are disabled.

## -returns

<b>KsFilterFactorySetDeviceClassesState</b> returns STATUS_SUCCESS or an error code.

## -remarks

This function is available in Windows XP and DirectX 8.0 and later.
