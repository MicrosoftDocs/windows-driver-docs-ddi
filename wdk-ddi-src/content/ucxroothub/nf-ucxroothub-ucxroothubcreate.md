---
UID: NF:ucxroothub.UcxRootHubCreate
tech.root: usbcon
title: UcxRootHubCreate
ms.date: 11/03/2022
targetos: Windows
description: Learn more about the UcxRootHubCreate function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ucxroothub.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
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
 - COM
api_location:
 - ucxroothub.h
api_name:
 - UcxRootHubCreate
f1_keywords:
 - UcxRootHubCreate
 - ucxroothub/UcxRootHubCreate
dev_langs:
 - c++
helpviewer_keywords:
 - UcxRootHubCreate
---

## -description

Creates a root hub object for the specified host controller.

## -parameters

### -param Controller [in]

A handle to the controller object. The client driver retrieved the handle in a previous call to [**UcxControllerCreate**](../ucxcontroller/nf-ucxcontroller-ucxcontrollercreate.md).

### -param Config [in]

A pointer to a [**UCX\_ROOTHUB\_CONFIG**](ns-ucxroothub-_ucx_roothub_config.md) structure that describes various configuration operations for creating the root hub object.

### -param Attributes [in, optional]

A pointer to a caller-allocated [**WDF\_OBJECT\_ATTRIBUTES**](../wdfobject/ns-wdfobject-_wdf_object_attributes.md) structure that specifies attributes for the root hub object.

### -param RootHub [out]

A pointer to a variable that receives a handle to the new root hub object.

## -returns

The method returns STATUS\_SUCCESS if the operation succeeds. Otherwise, this method might return one an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) error code.

## -remarks

The client driver for the host controller must call this method after the [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md) call. The parent of the new root hub object is the controller object.

Before calling this method, the client driver must initialize a [**UCX\_ROOTHUB\_CONFIG**](ns-ucxroothub-_ucx_roothub_config.md) structure by calling [**UCX\_ROOTHUB\_CONFIG\_INIT**](nf-ucxroothub-ucx_roothub_config_init_with_control_urb_handler.md). Supply function pointers to driver-supplied event callback implementations by call setting appropriate members of **UCX\_ROOTHUB\_CONFIG**. When events occur in the root hub object, UCX invokes those callback functions.

## Examples

```cpp
    UCX_ROOTHUB_CONFIG                      ucxRootHubConfig;
    UCXROOTHUB                              ucxRootHub;
    PUCX_ROOTHUB_CONTEXT                    ucxRootHubContext;
  

    // Create the root hub
    //
    UCX_ROOTHUB_CONFIG_INIT(&ucxRootHubConfig,
                            RootHub_EvtRootHubClearHubFeature,
                            RootHub_EvtRootHubClearPortFeature,
                            RootHub_EvtRootHubGetHubStatus,
                            RootHub_EvtRootHubGetPortStatus,
                            RootHub_EvtRootHubSetHubFeature,
                            RootHub_EvtRootHubSetPortFeature,
                            RootHub_EvtRootHubGetPortErrorCount,
                            RootHub_EvtRootHubInterruptTx,
                            RootHub_EvtRootHubGetInfo,
                            RootHub_EvtRootHubGet20PortInfo,
                            RootHub_EvtRootHubGet30PortInfo);

    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&objectAttributes, UCX_ROOTHUB_CONTEXT);

    status = UcxRootHubCreate(ucxController,
                              &ucxRootHubConfig,
                              &objectAttributes,
                              &ucxRootHub);

    if (!NT_SUCCESS(status)) {
        DbgTrace(TL_ERROR, Controller, "UcxRootHubCreate Failed %!STATUS!", status);
        goto Controller_WdfEvtDeviceAddEnd;
    }

    DbgTrace(TL_INFO, Controller, "UCX Root Hub created.");

    ucxControllerContext->UcxRootHub = ucxRootHub;

    ucxRootHubContext = GetUcxRootHubContext(ucxRootHub);
    ucxRootHubContext->UcxController = ucxController;
```

## -see-also

[**UCX\_ROOTHUB\_CONFIG**](ns-ucxroothub-_ucx_roothub_config.md)
