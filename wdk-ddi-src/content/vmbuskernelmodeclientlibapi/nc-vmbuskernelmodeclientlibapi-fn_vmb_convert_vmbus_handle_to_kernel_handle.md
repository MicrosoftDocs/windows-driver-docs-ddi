---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CONVERT_VMBUS_HANDLE_TO_KERNEL_HANDLE
title: FN_VMB_CONVERT_VMBUS_HANDLE_TO_KERNEL_HANDLE (vmbuskernelmodeclientlibapi.h)
description: The VmbConvertVmbusHandleToKernelHandle function converts the user mode VMBus handle to kernel mode handle.
tech.root: netvista
ms.assetid: cabb88f4-baa8-494a-88d1-d5aa4f53c45a
ms.date: 05/22/2018
ms.topic: callback
f1_keywords:
 - "vmbuskernelmodeclientlibapi/FN_VMB_CONVERT_VMBUS_HANDLE_TO_KERNEL_HANDLE"
req.header: vmbuskernelmodeclientlibapi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
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
- UserDefined
api_location: 
- vmbuskernelmodeclientlibapi.h
api_name: 
- FN_VMB_CONVERT_VMBUS_HANDLE_TO_KERNEL_HANDLE
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# FN_VMB_CONVERT_VMBUS_HANDLE_TO_KERNEL_HANDLE callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbConvertVmbusHandleToKernelHandle</b> function converts the user mode VMBus handle to kernel mode handle. 

## -prototype

```cpp
//Declaration

FN_VMB_CONVERT_VMBUS_HANDLE_TO_KERNEL_HANDLE FnVmbConvertVmbusHandleToKernelHandle; 

// Definition

NTSTATUS FnVmbConvertVmbusHandleToKernelHandle 
(
	HANDLE VmbusHandle
	PHANDLE KernelHandle
)
{...}

```

## -parameters

### -param VmbusHandle

The user-mode handle to convert. This must have been was opened in the virtual machine worker process.

### -param KernelHandle 

The kernel handle that references the same object as the <i>VmbusHandle</i> value.

## -returns

Returns STATUS_SUCCESS if the operation succeeds, or an appropriate NTSTATUS error code otherwise.

## -remarks

The
caller is responsible for closing the kernel handle.

Because the <i>VmbusHandle</i> parameter is a user-mode
handle, this function must be called in the context of the user-mode process which
opened the VMBus handle.

  Calling this function is often immediately followed by calling
the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbserverchannelinitsetvmbushandle">VmbServerChannelInitSetVmbusHandle</a> function.

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a server-only function accessed from the [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md) structure. 
>
> For more information, see the Remarks section of [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md).

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbserverchannelinitsetvmbushandle">VmbServerChannelInitSetVmbusHandle</a>
