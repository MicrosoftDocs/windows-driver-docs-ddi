---
UID: NF:mbbcx.MBB_DEVICE_CONFIG_INIT
title: MBB_DEVICE_CONFIG_INIT function
author: windows-driver-content
description: The MBB_DEVICE_CONFIG_INIT method initializes the MBB_DEVICE_CONFIG structure.
ms.assetid: 4ee1d631-e2b2-4080-bec2-8be7c1c9a166
ms.author: windowsdriverdev
ms.date: 06/26/2018
ms.topic: function
ms.keywords: MBB_DEVICE_CONFIG_INIT
req.header: mbbcx.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver:
req.lib: mbbcxstub.lib
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
-	LibDef
api_location: 
-	mbbcxstub.lib
api_name: 
-	MBB_DEVICE_CONFIG_INIT
product: Windows
targetos: Windows


---

# MBB_DEVICE_CONFIG_INIT function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
> 
> MBBCx is preview only in Windows 10, version 1809.

The **MBB_DEVICE_CONFIG_INIT** method initializes the [**MBB_DEVICE_CONFIG**](ns-mbbcx-_mbb_device_config.md) structure.

## -parameters

### -param Config

A pointer to the client driver-allocated [**MBB_DEVICE_CONFIG**](ns-mbbcx-_mbb_device_config.md) structure.

### -param SendMbimFragment

A pointer to the client driver's implementation of the [*EVT_MBB_DEVICE_SEND_MBIM_FRAGMENT*](nc-mbbcx-evt_mbb_device_send_mbim_fragment.md) callback function.

### -param ReceiveMbimFragment

A pointer to the client driver's implementation of the [*EVT_MBB_DEVICE_RECEIVE_MBIM_FRAGMENT*](nc-mbbcx-evt_mbb_device_receive_mbim_fragment.md) callback function.

### -param SendDeviceServiceSessionData

A pointer to the client driver's implementation of the [*EVT_MBB_DEVICE_SEND_SERVICE_SESSION_DATA*](nc-mbbcx-evt_mbb_device_send_device_service_session_data.md) callback function.

### -param CreateAdapter

A pointer to the client driver's implementation of the [*EVT_MBB_DEVICE_CREATE_ADAPTER*](nc-mbbcx-evt_mbb_device_create_adapter.md) callback function.

## -returns

This method does not return a value.

## -remarks

The client driver calls this method from its [*EVT_WDF_DRIVER_DEVICE_ADD*](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md) event callback function in preparation for calling [**MbbDeviceInitialize**](nf-mbbcx-mbbdeviceinitialize.md).

## -see-also

[Mobile Broadband (MBB) WDF class extension (MBBCx)](https://docs.microsoft.com/windows-hardware/drivers/netcx/mobile-broadband-mbb-wdf-class-extension-mbbcx)