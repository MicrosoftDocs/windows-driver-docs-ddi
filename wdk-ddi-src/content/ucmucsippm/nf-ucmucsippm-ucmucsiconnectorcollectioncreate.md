---
UID: NF:ucmucsippm.UcmUcsiConnectorCollectionCreate
title: UcmUcsiConnectorCollectionCreate function (ucmucsippm.h)
tech.root: usbref
description: Creates a connector collection object with UcmUcsiCx.
ms.assetid: 60a87133-87f2-4f4a-92b7-78c2562b88f5
ms.date: 09/30/2018
ms.topic: function
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
topic_type: 
- apiref
api_type: 
- LibDef
api_location: 
- UcmUcsiCxStub.lib
api_name: 
- UcmUcsiConnectorCollectionCreate
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# UcmUcsiConnectorCollectionCreate function


## -description
Creates a connector collection object with UcmUcsiCx.

## -parameters

### -param WdfDevice [in]
A handle to a framework device object that the client driver received in the previous call to [**WdfDeviceCreate**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicecreate).

### -param Attributes  [in]
A pointer to a caller-supplied [WDF_OBJECT_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes) structure that contains attributes for the new connector collection object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.

### -param ConnectorCollection [out]
A pointer to a location that receives a handle to the new connector collection object.

## -returns
Returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return an appropriate [NTSTATUS](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values) value.

## -remarks
The collection object is required for creating a Platform Policy Manager (PPM) object. The client driver creates the object by calling [**UcmUcsiPpmCreate**](nf-ucmucsippm-ucmucsippmcreate.md). The driver must not call [**UcmUcsiConnectorCollectionCreate**] after **UcmUcsiPpmCreate** because it would have no effect on the already existing PPM object.

The connector collection object is parented to the WDFOBJECT even when UcmUcsiConnectorCollectionCreate is called by passing WDF_NO_ATTRIBUTES. The lifetime of the object is manager by the framework.

## -see-also
[**WdfDeviceCreate**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicecreate)

[WDF_OBJECT_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes)

[**UcmUcsiPpmCreate**](nf-ucmucsippm-ucmucsippmcreate.md)

[**UcmUcsiConnectorCollectionAddConnector**](nf-ucmucsippm-ucmucsiconnectorcollectionaddconnector.md)
