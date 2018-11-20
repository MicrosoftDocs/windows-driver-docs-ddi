---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_SAVE_BEGIN
title: FN_VMB_CHANNEL_SAVE_BEGIN
author: windows-driver-content
description: The VmbChannelSaveBegin function initializes the context for saving the state of a channel. The driver must check the return value of the function.
tech.root: netvista
ms.assetid: 986669ad-e997-4850-a9b1-b45d6f1497cd
ms.date: 05/21/2018
ms.topic: callback
req.header: vmbuskernelmodeclientlibapi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
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
-	apiref
api_type: 
-	UserDefined
api_location: 
-	vmbuskernelmodeclientlibapi.h
api_name: 
-	FN_VMB_CHANNEL_SAVE_BEGIN
product:
-	Windows
targetos: Windows
ms.custom: RS5
---

# FN_VMB_CHANNEL_SAVE_BEGIN callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelSaveBegin</b> function initializes the context for saving the state of a channel. The driver must check the return value of the function.

## -prototype

```cpp
//Declaration

FN_VMB_CHANNEL_SAVE_BEGIN FnVmbChannelSaveBegin; 

// Definition

NTSTATUS FnVmbChannelSaveBegin 
(
	VMBCHANNEL Channel
)
{...}

```

## -parameters

### -param Channel 

A handle for the channel to save.

## -returns

Returns STATUS_SUCCESS if the operation succeeded, or an appropriate NTSTATUS error code otherwise.

## -remarks

The
caller next calls the <a href="https://msdn.microsoft.com/57266CAE-C069-4379-92FD-0F93FECC6EB5"> VmbChannelSaveContinue</a> function multiple times until
all the state is saved, and then calls the <a href="https://msdn.microsoft.com/0E61AF98-DC71-4234-B337-71B2AF65D858">VmbChannelSaveEnd</a> function.

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a server-only function accessed from the [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md) structure. 
>
> For more information, see the Remarks section of [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md).

## -see-also

<a href="https://msdn.microsoft.com/57266CAE-C069-4379-92FD-0F93FECC6EB5"> VmbChannelSaveContinue</a>



<a href="https://msdn.microsoft.com/0E61AF98-DC71-4234-B337-71B2AF65D858">VmbChannelSaveEnd</a>
