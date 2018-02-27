---
UID: NA:ndisndk
ms.assetid: 97423041-9168-37e0-a61d-87a83c72d7af
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ndisndk.h header



This header is used by Networking drivers for Windows Vista and later. For more information, see
- [Networking drivers for Windows Vista and later](../_netvista/index.md)

Ndisndk.h contain these programming interfaces:


## Callback functions

| Title   | Description   |
| ---- |:---- |
| [CLOSE_NDK_ADAPTER_HANDLER callback](nc-ndisndk-close_ndk_adapter_handler.md) | The CloseNDKAdapterHandler (CLOSE_NDK_ADAPTER_HANDLER) function closes an NDK adapter instance on an NDK-capable NDIS miniport adapter. |
| [OPEN_NDK_ADAPTER_HANDLER callback](nc-ndisndk-open_ndk_adapter_handler.md) | The OpenNDKAdapterHandler (OPEN_NDK_ADAPTER_HANDLER) function opens an NDK adapter instance on an NDK-capable NDIS miniport adapter. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_NDIS_NDK_PROVIDER_CHARACTERISTICS structure](ns-ndisndk-_ndis_ndk_provider_characteristics.md) | The NDIS_NDK_PROVIDER_CHARACTERISTICS structure specifies NDK provider characteristics. |
| [_NDIS_OPEN_NDK_ADAPTER_PARAMETERS structure](ns-ndisndk-_ndis_open_ndk_adapter_parameters.md) | The NDIS_OPEN_NDK_ADAPTER_PARAMETERS structure specifies parameters to open an NDK adapter instance on the NDK-capable miniport adapter. |
