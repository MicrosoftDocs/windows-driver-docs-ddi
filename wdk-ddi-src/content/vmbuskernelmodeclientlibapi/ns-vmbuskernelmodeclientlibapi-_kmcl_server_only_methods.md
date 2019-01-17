---
UID: NS:vmbuskernelmodeclientlibapi._KMCL_SERVER_ONLY_METHODS
title: _KMCL_SERVER_ONLY_METHODS
description: The KMCL_SERVER_ONLY_METHODS structure contains function pointers for server-only functions for the VMBus Kernel Mode Client Library (KMCL) interface.
ms.assetid: ef9df9ca-b6d0-4c8e-a482-7989bab40b40
ms.date: 09/13/2018
ms.topic: struct
ms.keywords: _KMCL_SERVER_ONLY_METHODS, KMCL_SERVER_ONLY_METHODS, 
req.header: vmbuskernelmodeclientlibapi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: KMCL_SERVER_ONLY_METHODS
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	vmbuskernelmodeclientlibapi.h
api_name: 
-	_KMCL_SERVER_ONLY_METHODS
product: 
- Windows
targetos: Windows
tech.root: netvista
ms.custom: RS5
---

# _KMCL_SERVER_ONLY_METHODS structure

## -description

The **KMCL_SERVER_ONLY_METHODS** structure contains function pointers for server-only functions for the VMBus Kernel Mode Client Library (KMCL) interface.

For more information about how to access the KMCL interface, see the Remarks section.

## -struct-fields

### -field VmbChannelMapGpadl

A pointer to the [**VmbChannelMapGpadl**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_map_gpadl.md) function.
 
### -field VmbChannelRestoreFromBuffer

A pointer to the [**VmbChannelRestoreFromBuffer**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_restore_from_buffer.md) function.
 
### -field VmbChannelSaveBegin

A pointer to the [**VmbChannelSaveBegin**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_save_begin.md) function.
 
### -field VmbChannelSaveContinue

A pointer to the [**VmbChannelSaveContinue**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_save_continue.md) function.
 
### -field VmbChannelSaveEnd

A pointer to the [**VmbChannelSaveEnd**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_save_end.md) function.
 
### -field VmbChannelUnmapGpadl

A pointer to the [**VmbChannelUnmapGpadl**](nc-vmbuskernelmodeclientlibapi-fn_vmb_channel_unmap_gpadl.md) function.
 
### -field VmbConvertVmbusHandleToKernelHandle

A pointer to the [**VmbConvertVmbusHandleToKernelHandle**](nc-vmbuskernelmodeclientlibapi-fn_vmb_convert_vmbus_handle_to_kernel_handle.md) function.
 
### -field VmbPacketRestore

A pointer to the [**VmbPacketRestore**](nc-vmbuskernelmodeclientlibapi-fn_vmb_packet_restore.md) function.
 
### -field VmbServerChannelInitSetFlags

A pointer to the [**VmbServerChannelInitSetFlags**](nc-vmbuskernelmodeclientlibapi-fn_vmb_server_channel_init_set_flags.md) function.
 
### -field VmbServerChannelInitSetMmioMegabytes

A pointer to the [**VmbServerChannelInitSetMmioMegabytes**](nc-vmbuskernelmodeclientlibapi-fn_vmb_server_channel_init_set_mmio_megabytes.md) function.
 
### -field VmbServerChannelInitSetSaveRestorePacketCallbacks

A pointer to the [**VmbServerChannelInitSetSaveRestorePacketCallbacks**](nc-vmbuskernelmodeclientlibapi-fn_vmb_server_channel_init_set_save_restore_packet_callbacks.md) function.
 
### -field VmbServerChannelInitSetTargetInterfaceId

A pointer to the [**VmbServerChannelInitSetTargetInterfaceId**](nc-vmbuskernelmodeclientlibapi-fn_vmb_server_channel_init_set_target_interface_id.md) function.
 
### -field VmbServerChannelInitSetTargetVtl

A pointer to the [**VmbServerChannelInitSetTargetVtl**](nc-vmbuskernelmodeclientlibapi-fn_vmb_server_channel_init_set_target_vtl.md) function.
 
### -field VmbServerChannelInitSetVmbusHandle

A pointer to the [**VmbServerChannelInitSetVmbusHandle**](nc-vmbuskernelmodeclientlibapi-fn_vmb_server_channel_init_set_vmbus_handle.md) function.

## -remarks

The function pointers in **KMCL_SERVER_ONLY_METHODS** are called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This structure contains function pointers for server-only functions. 

To access both client and server-only functions of the KMCL interface, allocate a **KMCL_SERVER_INTERFACE_V1** structure to receive the interface, then call either [**WdfFdoQueryForInterface**](../wdffdo/nf-wdffdo-wdffdoqueryforinterface.md) or [**WdfIoTargetQueryForInterface**](../wdfiotarget/nf-wdfiotarget-wdfiotargetqueryforinterface.md) with these parameters:
 
- *InterfaceType* parameter: **KMCL_SERVER_INTERFACE_TYPE**
- *Size* parameter: `sizeof(KMCL_SERVER_INTERFACE_V1)`
- *Version* parameter: **KMCL_SERVER_INTERFACE_VERSION_V1** 

The **KMCL_SERVER_INTERFACE_V1** structure is defined as follows for C language code:

```C++
typedef struct _KMCL_SERVER_INTERFACE_V1 {
    KMCL_CLIENT_INTERFACE_V1;
    KMCL_SERVER_ONLY_METHODS;
} KMCL_SERVER_INTERFACE_V1, *PKMCL_SERVER_INTERFACE_V1;
```

If the interface query function succeeds, the **KMCL_SERVER_INTERFACE_V1** structure contains both a [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure and a  **KMCL_SERVER_ONLY_METHODS** structure. The **KMCL_SERVER_ONLY_METHODS** structure contains function pointers that you can use to call VMBus KMCL server-only functions.

For KMCL client methods, see the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure.

For more information about driver-defined interfaces, see [Using Driver-Defined Interfaces](https://docs.microsoft.com/windows-hardware/drivers/wdf/using-driver-defined-interfaces).

## -see-also

[Using Driver-Defined Interfaces](https://docs.microsoft.com/windows-hardware/drivers/wdf/using-driver-defined-interfaces)

[**WdfFdoQueryForInterface**](../wdffdo/nf-wdffdo-wdffdoqueryforinterface.md)

[**WdfIoTargetQueryForInterface**](../wdfiotarget/nf-wdfiotarget-wdfiotargetqueryforinterface.md)

[**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md)
