---
UID: NA:wdfqueryinterface
ms.assetid: f1e1f714-ecee-3288-bb22-75c85c09b214
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wdfqueryinterface.h header



This header is used by Windows Driver Framework. For more information, see
- [Windows Driver Framework](../_wdf/index.md)

Wdfqueryinterface.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [WDF_QUERY_INTERFACE_CONFIG_INIT function](nf-wdfqueryinterface-wdf_query_interface_config_init.md) | The WDF_QUERY_INTERFACE_CONFIG_INIT function initializes a driver's WDF_QUERY_INTERFACE_CONFIG structure. |
| [WdfDeviceAddQueryInterface function](nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md) | The WdfDeviceAddQueryInterface method creates a driver-defined interface that other drivers can query and use. |
| [WdfDeviceInterfaceDereferenceNoOp function](nf-wdfqueryinterface-wdfdeviceinterfacedereferencenoop.md) | The WdfDeviceInterfaceDereferenceNoOp method can be used for driver-defined interfaces that do not require reference counts. |
| [WdfDeviceInterfaceReferenceNoOp function](nf-wdfqueryinterface-wdfdeviceinterfacereferencenoop.md) | The WdfDeviceInterfaceReferenceNoOp method can be used for driver-defined interfaces that do not require reference counts. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_WDF_QUERY_INTERFACE_CONFIG structure](ns-wdfqueryinterface-_wdf_query_interface_config.md) | The WDF_QUERY_INTERFACE_CONFIG structure describes a driver-defined interface. |
