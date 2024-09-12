---
UID: NC:fltkernel.PFLT_CONNECT_NOTIFY
tech.root: ifsk
title: PFLT_CONNECT_NOTIFY
ms.date: 07/10/2024
targetos: Windows
description: Learn about the PFLT_CONNECT_NOTIFY callback function.
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
 - PFLT_CONNECT_NOTIFY
f1_keywords:
 - PFLT_CONNECT_NOTIFY
 - fltkernel/PFLT_CONNECT_NOTIFY
dev_langs:
 - c++
helpviewer_keywords:
 - PFLT_CONNECT_NOTIFY
---

## -description

*FltMgr* calls a minifilter's **ConnectNotifyCallback** callback function to notify the minifilter when a new connection to a communication port is being requested.

## -parameters

### -param ClientPort

[in] Opaque, *FltMgr*-generated handle for the new client port that is being established between the user-mode application and the kernel-mode minifilter.

The minifilter must pass this handle as the **ClientPort** parameter to [**FltSendMessage**](nf-fltkernel-fltsendmessage.md) when sending and replying to messages on this client port.

The minifilter must eventually call [**FltCloseClientPort**](nf-fltkernel-fltcloseclientport.md) to close this client port, typically from its [**DisconnectNotifyCallback**](nc-fltkernel-pflt_disconnect_notify.md) routine.

**ClientPort** isn't the same as the **ServerPort** handle return by[**FltCreateCommunicationPort**](nf-fltkernel-fltcreatecommunicationport.md).

### -param ServerPortCookie

[in] Pointer to context information defined by the minifilter. The minifilter can use this information to distinguish among multiple communication server ports that it might create. When the server port was created, the minifilter driver passed this context pointer as the **ServerPortCookie** parameter to **FltCreateCommunicationPort**.

### -param ConnectionContext

[in] Context information pointer that the user-mode application passed in the **lpContext** parameter to [**FilterConnectCommunicationPort**](/windows/win32/api/fltuser/nf-fltuser-filterconnectcommunicationport).

### -param SizeOfContext

[in] Size, in bytes, of the buffer that **ConnectionContext** points to.

### -param ConnectionPortCookie

[out] Pointer to the miniport's information that uniquely identifies this client port. The minifilter can use this cookie to identify the connection when *FltMgr* passes it in subsequent calls to [**MessageNotifyCallback**](nc-fltkernel-pflt_message_notify.md) and [**DisconnectNotifyCallback**](nc-fltkernel-pflt_disconnect_notify.md).

## -returns

**ConnectNotifyCallback** returns STATUS_SUCCESS if the operation succeeds and the connection has been accepted. Otherwise, it returns an appropriate NTSTATUS value such as:

| Return code | Meaning |
| ----------- | ------- |
| STATUS_INSUFFICIENT_RESOURCES | There aren't enough resources to complete the operation. |
| STATUS_INVALID_PARAMETER | One or more of the input parameters are invalid. |

## -remarks

*FltMgr* calls this routine whenever a user-mode application calls [**FilterConnectCommunicationPort**](/windows/win32/api/fltuser/nf-fltuser-filterconnectcommunicationport) to send a connection request to the minifilter driver.

The minifilter should perform any necessary validation of the connection attempt.

For more information, see [Communication between user-mode and minifilters](/windows-hardware/drivers/ifs/communication-between-user-mode-and-kernel-mode).

## -see-also

[**FilterConnectCommunicationPort**](/windows/win32/api/fltuser/nf-fltuser-filterconnectcommunicationport)

[**FltCloseClientPort**](nf-fltkernel-fltcloseclientport.md)

[**FltCreateCommunicationPort**](nf-fltkernel-fltcreatecommunicationport.md)

[**FltSendMessage**](nf-fltkernel-fltsendmessage.md)

[**DisconnectNotifyCallback**](nc-fltkernel-pflt_disconnect_notify.md)

[**MessageNotifyCallback**](nc-fltkernel-pflt_message_notify.md)
