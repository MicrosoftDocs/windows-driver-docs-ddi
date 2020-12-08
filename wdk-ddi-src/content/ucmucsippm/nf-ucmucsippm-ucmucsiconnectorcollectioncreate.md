---
UID: NF:ucmucsippm.UcmUcsiConnectorCollectionCreate
title: UcmUcsiConnectorCollectionCreate function (ucmucsippm.h)
tech.root: usbref
description: Creates a connector collection object with UcmUcsiCx.
ms.date: 09/30/2018
keywords: ["UcmUcsiConnectorCollectionCreate function"]
ms.keywords: UcmUcsiConnectorCollectionCreate
req.header: ucmucsippm.h
req.include-header: UcmUcsiCx.h
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.27
req.umdf-ver: N/A
req.lib: UcmUcsiCxStub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: RS5
f1_keywords:
 - UcmUcsiConnectorCollectionCreate
 - ucmucsippm/UcmUcsiConnectorCollectionCreate
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - UcmUcsiCxStub.lib
api_name:
 - UcmUcsiConnectorCollectionCreate
---

# UcmUcsiConnectorCollectionCreate function


## -description

Creates a connector collection object with UcmUcsiCx.

## -parameters

### -param WdfDevice 

[in]A handle to a framework device object that the client driver received in the previous call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

### -param Attributes  

[in]A pointer to a caller-supplied [WDF_OBJECT_ATTRIBUTES](../wdfobject/ns-wdfobject-_wdf_object_attributes.md) structure that contains attributes for the new connector collection object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.

### -param ConnectorCollection 

[out]A pointer to a location that receives a handle to the new connector collection object.

## -returns

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) value.

## -remarks

The collection object is required for creating a Platform Policy Manager (PPM) object. The client driver creates the object by calling [**UcmUcsiPpmCreate**](nf-ucmucsippm-ucmucsippmcreate.md). The driver must not call [**UcmUcsiConnectorCollectionCreate**] after **UcmUcsiPpmCreate** because it would have no effect on the already existing PPM object.

The connector collection object is parented to the WDFOBJECT even when UcmUcsiConnectorCollectionCreate is called by passing WDF_NO_ATTRIBUTES. The lifetime of the object is manager by the framework.

## -see-also

[**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md)

[WDF_OBJECT_ATTRIBUTES](../wdfobject/ns-wdfobject-_wdf_object_attributes.md)

[**UcmUcsiPpmCreate**](nf-ucmucsippm-ucmucsippmcreate.md)

[**UcmUcsiConnectorCollectionAddConnector**](nf-ucmucsippm-ucmucsiconnectorcollectionaddconnector.md)
