---
UID: NC:fltkernel.PFLT_DISCONNECT_NOTIFY
tech.root: ifsk
title: PFLT_DISCONNECT_NOTIFY
ms.date: 07/10/2024
targetos: Windows
description: Learn about the PFLT_DISCONNECT_NOTIFY callback function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: FltMgr.sys
req.header: fltkernel.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL 
req.kmdf-ver: 
req.lib: FltMgr.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - fltkernel.h
api_name:
 - PFLT_DISCONNECT_NOTIFY
f1_keywords:
 - PFLT_DISCONNECT_NOTIFY
 - fltkernel/PFLT_DISCONNECT_NOTIFY
dev_langs:
 - c++
helpviewer_keywords:
 - PFLT_DISCONNECT_NOTIFY
---

## -description

*FltMgr* calls a minifilter's **DisconnectNotifyCallback** callback function to notify the minifilter when a client port is being disconnected.

## -parameters

### -param ConnectionCookie

[in] Pointer to minifilter-defined information that uniquely identifies this client port. When the client port was created, the minifilter returned this context pointer in the **ConnectionPortCookie** parameter of its [**ConnectNotifyCallback**](nc-fltkernel-pflt_connect_notify.md) routine.

## -remarks

*FltMgr* calls **DisconnectNotifyCallback** whenever the user-mode handle count for the client port reaches zero or when the minifilter is about to be unloaded.

For more information, see [Communication between user-mode and minifilters](/windows-hardware/drivers/ifs/communication-between-user-mode-and-kernel-mode).

## -see-also

[**ConnectNotifyCallback**](nc-fltkernel-pflt_connect_notify.md)

[**FltCreateCommunicationPort**](nf-fltkernel-fltcreatecommunicationport.md)
