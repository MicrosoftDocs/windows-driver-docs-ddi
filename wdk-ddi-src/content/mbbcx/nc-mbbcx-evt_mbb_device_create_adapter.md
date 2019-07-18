---
UID: NC:mbbcx.EVT_MBB_DEVICE_CREATE_ADAPTER
title: EVT_MBB_DEVICE_CREATE_ADAPTER (mbbcx.h)
description: The EvtMbbDeviceCreateAdapter callback function is implemented by the client driver to create a NETADAPTER object for a data session.
tech.root: netvista
ms.assetid: db841566-dd24-4687-b00c-1bf2a22f4243
ms.date: 02/06/2019
ms.topic: callback
f1_keywords:
 - "mbbcx/-	EVT_MBB_DEVICE_CREATE_ADAPTER"
req.header: mbbcx.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver: 1.29
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	mbbcx.h
api_name: 
-	EVT_MBB_DEVICE_CREATE_ADAPTER
product:
- Windows
targetos: Windows
ms.custom: 19H1
---

# EVT_MBB_DEVICE_CREATE_ADAPTER callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
> 
> MBBCx is preview only in Windows 10, version 1903.

The *EvtMbbDeviceCreateAdapter* callback function is implemented by the client driver to create a NETADAPTER object for a data session.

## -prototype

```cpp
//Declaration

EVT_MBB_DEVICE_CREATE_ADAPTER EvtMbbDeviceCreateAdapter; 

// Definition

NTSTATUS EvtMbbDeviceCreateAdapter 
(
	WDFDEVICE			Device,
	NETADAPTER_INIT *	AdapterInit
)
{...}

```

## -parameters

### -param Device

A handle to a framework device object the client driver obtained from a previous call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

### -param AdapterInit

A NETADAPTER_INIT object that describes the initialization information for the NETADAPTER.

## -returns

This callback function returns STATUS_SUCCESS if the operation was successful. Otherwise, it returns an appropriate NTSTATUS error code.

## -remarks

An MBBCx client driver must register an *EvtMbbDeviceCreateAdapter* callback function by calling [**MbbDeviceInitialize**](nf-mbbcx-mbbdeviceinitialize.md).

In this callback, the client driver creates a NETADAPTER object that is used by MBBCx to represent the network interface for a data session. MBBCx invokes this callback function at least once to establish the primary PDP context/default EPS bearer, then it might invoke it more times, once for every data session to be established.

Before returning from *EvtMbbDeviceCreateAdapter*, client drivers must start the adapter by calling [**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md). Optionally, they can also set the adapter's capabilities by calling one or more of these functions *before* the call to **NetAdapterStart**: 

- [**NetAdapterSetDatapathCapabilities**](../netadapter/nf-netadapter-netadaptersetdatapathcapabilities.md)
- [**NetAdapterSetLinkLayerCapabilities**](../netadapter/nf-netadapter-netadaptersetlinklayercapabilities.md)
- [**NetAdapterSetLinkLayerMtuSize**](../netadapter/nf-netadapter-netadaptersetlinklayermtusize.md)
- [**NetAdapterSetPowerCapabilities**](../netadapter/nf-netadapter-netadaptersetpowercapabilities.md)

For more information and a code example, see [Creating the NetAdapter interface for the PDP context/EPS bearer](https://docs.microsoft.com/windows-hardware/drivers/netcx/writing-an-mbbcx-client-driver#creating-the-netadapter-interface-for-the-pdp-contexteps-bearer).

## -see-also
