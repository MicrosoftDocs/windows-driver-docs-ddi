---
UID: NF:ucmucsippm.UcmUcsiConnectorCollectionAddConnector
title: UcmUcsiConnectorCollectionAddConnector function
author: windows-driver-content
tech.root: usbref
description: Adds a connector to the connector collection object.
ms.assetid: 0b8f9d0c-60c8-467d-9575-833c87f45bb6
ms.date: 09/30/2018
ms.topic: function
ms.keywords: UcmUcsiConnectorCollectionAddConnector
req.header: Ucmucsippm.h
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
-	apiref
api_type: 
-	LibDef
api_location: 
-	UcmUcsiCxStub.lib
api_name: 
-	UcmUcsiConnectorCollectionAddConnector
product: Windows
targetos: Windows


---

# UcmUcsiConnectorCollectionAddConnector function


## -description

Adds a connector to the connector collection object.

## -parameters

### -param ConnectorCollectionObject [in]
The handle to the connector collection object that the client driver retrieved in a previous call to [**UcmUcsiConnectorCollectionCreate**](nf-ucmucsippm-ucmucsiconnectorcollectioncreate.md).

### -param ConnectorInfo [in]
A pointer to a [**UCMUCSI_CONNECTOR_INFO**](ns-ucmucsippm-_ucmucsi_connector_info.md) structure that contains information about the connector to add.

## -returns
Returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return an appropriate [NTSTATUS](https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505) value.

## -remarks
The client driver must not call **UcmUcsiConnectorCollectionAddConnector** after [**UcmUcsiPpmCreate**](nf-ucmucsippm-ucmucsippmcreate.md) because it would have no effect on the already existing PPM object.


## -see-also

[**UCMUCSI_CONNECTOR_INFO**](ns-ucmucsippm-_ucmucsi_connector_info.md)

[**UcmUcsiConnectorCollectionCreate**](nf-ucmucsippm-ucmucsiconnectorcollectioncreate.md)

[**UcmUcsiPpmCreate**](nf-ucmucsippm-ucmucsippmcreate.md)
