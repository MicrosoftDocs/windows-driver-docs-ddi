---
UID: NF:ucxroothub.UCX_ROOTHUB_CONFIG_INIT_WITH_CONTROL_URB_HANDLER
tech.root: usbcon
title: UCX_ROOTHUB_CONFIG_INIT_WITH_CONTROL_URB_HANDLER
ms.date: 11/03/2022
targetos: Windows
description: Learn more about the UCX_ROOTHUB_CONFIG_INIT_WITH_CONTROL_URB_HANDLER function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ucxroothub.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ucxroothub.h
api_name:
 - UCX_ROOTHUB_CONFIG_INIT_WITH_CONTROL_URB_HANDLER
f1_keywords:
 - UCX_ROOTHUB_CONFIG_INIT_WITH_CONTROL_URB_HANDLER
 - ucxroothub/UCX_ROOTHUB_CONFIG_INIT_WITH_CONTROL_URB_HANDLER
dev_langs:
 - c++
helpviewer_keywords:
 - UCX_ROOTHUB_CONFIG_INIT_WITH_CONTROL_URB_HANDLER
---

## -description

Initializes a [**UCX\_ROOTHUB\_CONFIG**](ns-ucxroothub-_ucx_roothub_config.md) with pointers to event callback functions implemented by the client driver.

## -parameters

### -param Config [out]

A pointer to a [**UCX\_ROOTHUB\_CONFIG**](ns-ucxroothub-_ucx_roothub_config.md) structure to initialize.

### -param EvtRootHubControlUrb [in]

A pointer to client driver's implementation of the [*EVT\_UCX\_ROOTHUB\_CONTROL\_URB*](nc-ucxroothub-evt_ucx_roothub_control_urb.md) event callback.

### -param EvtRootHubInterruptTx [in]

A pointer to client driver's implementation of the [*EVT\_UCX\_ROOTHUB\_INTERRUPT\_TX*](nc-ucxroothub-evt_ucx_roothub_interrupt_tx.md) event callback.

### -param EvtRootHubGetInfo [in]

A pointer to client driver's implementation of the [*EVT\_UCX\_ROOTHUB\_GET\_INFO*](nc-ucxroothub-evt_ucx_roothub_get_info.md) event callback.

### -param EvtRootHubGet20PortInfo [in]

A pointer to client driver's implementation of the [*EVT\_UCX\_ROOTHUB\_GET\_20PORT\_INFO*](nc-ucxroothub-evt_ucx_roothub_get_20port_info.md) event callback.

### -param EvtRootHubGet30PortInfo [in]

A pointer to client driver's implementation of the [*EVT\_UCX\_ROOTHUB\_GET\_30PORT\_INFO*](nc-ucxroothub-evt_ucx_roothub_get_30port_info.md) event callback.

## -remarks

This function does not return a value.

## -see-also

[**UcxRootHubCreate**](nf-ucxroothub-ucxroothubcreate.md)
