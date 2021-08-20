---
UID: NF:wificx.WifiDeviceGetOsWdiVersion
tech.root: netvista
title: WifiDeviceGetOsWdiVersion (wificx.h)
ms.date: 04/30/2021
ms.topic: language-reference
targetos: Windows
description: The WifiDeviceGetOsWdiVersion function gets the TLV version that WifiCx uses to initialize client driver's TLV parser/generator.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wificx.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wificx.h
api_name:
 - WifiDeviceGetOsWdiVersion
f1_keywords:
 - WifiDeviceGetOsWdiVersion
 - wificx/WifiDeviceGetOsWdiVersion
dev_langs:
 - c++
---

## -description

The **WifiDeviceGetOsWdiVersion** function gets the TLV version that WifiCx uses to initialize client driver's [TLV parser/generator](/windows-hardware/drivers/netcx/wificx-tlv-generator-parser).

## -parameters

### -param Device

[_In_] A handle to a framework device object that the client driver obtained from a previous call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

## -returns

Returns the TLV version that WifiCx uses to initialize client driver's TLV parser/generator.

## -remarks

## -see-also

[WiFiCx TLV parser/generator](/windows-hardware/drivers/netcx/wificx-tlv-generator-parser)

[**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md)