---
UID: NC:wsk.PFN_WSK_SEND_MESSAGES
tech.root: netvista
title: PFN_WSK_SEND_MESSAGES
ms.date: 08/02/2021
targetos: Windows
description: The WskSendMessages function sends multiple datagrams to the specified remote entity or group from the specified datagram socket.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wsk.h
req.idl: 
req.include-header: wsk.h
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 8
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
 - wsk.h
api_name:
 - PFN_WSK_SEND_MESSAGES
f1_keywords:
 - PFN_WSK_SEND_MESSAGES
 - wsk/PFN_WSK_SEND_MESSAGES
dev_langs:
 - c++
---

## -description

The **WskSendMessages** function sends multiple datagrams to the specified remote entity or group from the specified datagram socket. The socket must have been bound to a local
address.

## -parameters

### -param Socket

[in] A pointer to a [**WSK_SOCKET**](ns-wsk-_wsk_socket.md) structure that specifies the socket
object to send the datagrams from.

### -param BufferList

[in] A pointer to an initialized [**WSK_BUF_LIST**](ns-wsk-_wsk_buf_list.md) structure that contains the list of datagrams to send.

### -param Flags

[Reserved] This parameter is reserved for system use. A WSK application must set this parameter to **zero**.

### -param RemoteAddress

[in, optional]
A pointer to a structure that specifies the remote transport address to send the datagrams to. 

### -param ControlInfoLength

[in] The number of bytes of data in the buffer that is pointed to by the **ControlInfo** parameter. If there is no control information associated with the datagram, the **ControlInfoLength** parameter must be **zero**.


### -param ControlInfo

[In_reads_bytes_opt]
A pointer to a buffer that contains control information that is associated with the datagrams that
are being sent. The control information data consists of one or more control data objects, each of which begins with a [**CMSGHDR**](/windows/win32/api/ws2def/ns-ws2def-wsacmsghdr) structure. If there is no control information that is associated with the datagrams, this parameter should be <b>NULL</b>.

**ControlInfo** may not be supported by all transports.

### -param Irp

[in, out]
A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the send operation asynchronously. For more information about using IRPs with WSK functions, see [Using IRPs with Winsock
Kernel Functions](/windows-hardware/drivers/network/using-irps-with-winsock-kernel-functions).


## -returns


|Return code|Description|
|--- |--- |
|**STATUS_SUCCESS**|The datagram was successfully sent over the socket. The IRP will be completed with success status. The **IoStatus.Information** field of the IRP contains the number of bytes that were sent.|
|**STATUS_PENDING**|The WSK subsystem could not send the datagrams over the socket immediately. The WSK subsystem will complete the IRP after it has sent the datagrams over the socket. The status of the send operation will be returned in the **IoStatus.Status** field of the IRP. If the operation succeeds, the **IoStatus.Information** field of the IRP will contain the number of bytes that were sent.|
|**FAILURES**|An error occurred. The IRP will be completed with failure status.|

## -remarks

## -see-also

[**WSK_SOCKET**](ns-wsk-_wsk_socket.md)

[**WSK_BUF_LIST**](ns-wsk-_wsk_buf_list.md)

[**CMSGHDR**](/windows/win32/api/ws2def/ns-ws2def-wsacmsghdr)

[Using IRPs with Winsock
Kernel Functions](/windows-hardware/drivers/network/using-irps-with-winsock-kernel-functions)