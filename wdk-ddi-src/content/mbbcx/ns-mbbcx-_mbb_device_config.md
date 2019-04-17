---
UID: NS:mbbcx._MBB_DEVICE_CONFIG
title: _MBB_DEVICE_CONFIG (mbbcx.h)
description: The MBB_DEVICE_CONFIG structure contains pointers to a client driver's MBBCx-specific callback functions. The client driver must supply an initialized MBB_DEVICE_CONFIG structure as an input parameter to MbbDeviceInitialize.
tech.root: netvista
ms.assetid: cfe5c009-9245-4d41-992d-5cc5ce2ab711
ms.date: 07/02/2018
ms.topic: struct
ms.keywords: _MBB_DEVICE_CONFIG, MBB_DEVICE_CONFIG, *PMBB_DEVICE_CONFIG, 
req.header: mbbcx.h
req.include-header:
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: MBB_DEVICE_CONFIG, *PMBB_DEVICE_CONFIG
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- mbbcx.h
api_name: 
- _MBB_DEVICE_CONFIG
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# _MBB_DEVICE_CONFIG structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
> 
> MBBCx is preview only in Windows 10, version 1903.

The **MBB_DEVICE_CONFIG** structure contains pointers to a client driver's MBBCx-specific callback functions. The client driver must supply an initialized **MBB_DEVICE_CONFIG** structure as an input parameter to [**MbbDeviceInitialize**](nf-mbbcx-mbbdeviceinitialize.md).

## -struct-fields

### -field Size

The size of this **MBB_DEVICE_CONFIG** structure, in bytes.
 
### -field SendMbimFragment

A pointer to the client driver's implementation of the [*EVT_MBB_DEVICE_SEND_MBIM_FRAGMENT*](nc-mbbcx-evt_mbb_device_send_mbim_fragment.md) callback function.
 
### -field ReceiveMbimFragment

A pointer to the client driver's implementation of the [*EVT_MBB_DEVICE_RECEIVE_MBIM_FRAGMENT*](nc-mbbcx-evt_mbb_device_receive_mbim_fragment.md) callback function.
 
### -field SendDeviceServiceSessionData

A pointer to the client driver's implementation of the [*EVT_MBB_DEVICE_SEND_SERVICE_SESSION_DATA*](nc-mbbcx-evt_mbb_device_send_device_service_session_data.md) callback function.
 
### -field CreateAdapter

A pointer to the client driver's implementation of the [*EVT_MBB_DEVICE_CREATE_ADAPTER*](nc-mbbcx-evt_mbb_device_create_adapter.md) callback function.

## -remarks

Call [**MBB_DEVICE_CONFIG_INIT**](nf-mbbcx-mbb_device_config_init.md) to intialize this structure.

## -see-also
