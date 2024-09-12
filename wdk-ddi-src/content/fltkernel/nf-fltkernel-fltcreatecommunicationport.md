---
UID: NF:fltkernel.FltCreateCommunicationPort
title: FltCreateCommunicationPort function (fltkernel.h)
description: Learn more about the FltCreateCommunicationPort function.
tech.root: ifsk
ms.date: 07/10/2024
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltCreateCommunicationPort
 - fltkernel/FltCreateCommunicationPort
helpviewer_keywords:
 - PFLT_CONNECT_NOTIFY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltCreateCommunicationPort
---

# FltCreateCommunicationPort function

## -description

**FltCreateCommunicationPort** creates a communication server port on which a minifilter can receive connection requests from user-mode applications and services.

## -parameters

### -param Filter

[in] Opaque filter pointer for the caller.

### -param ServerPort

[out] Pointer to a caller-allocated variable that receives an opaque port handle for the communication server port. The minifilter uses this handle to listen for incoming connection requests from a user-mode application.

### -param ObjectAttributes

[in] Pointer to an [**OBJECT_ATTRIBUTES**](/windows/win32/api/ntdef/ns-ntdef-_object_attributes) structure that specifies the attributes of the communication server port. This structure must have been initialized by a previous call to [**InitializeObjectAttributes**](/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes). This parameter is required and can't be NULL. Members of this structure for a communication port object include the following.

| Member | Value |
| ------ | ----- |
| **Length** | [**InitializeObjectAttributes**](/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes) sets this member to ```sizeof(OBJECT_ATTRIBUTES)```. |
| **ObjectName** | Pointer to a [**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure containing a unique name (for example, L"\\MyFilterPort") for the port object. |
| **SecurityDescriptor** | Pointer to a security descriptor ([**SECURITY_DESCRIPTOR**](../ntifs/ns-ntifs-_security_descriptor.md)) to be applied to the port object. If needed, a default security descriptor can be created by calling [**FltBuildDefaultSecurityDescriptor**](nf-fltkernel-fltbuilddefaultsecuritydescriptor.md). |
| **Attributes** | Bitmask of flags specifying the desired attributes for the port handle. These flags must include OBJ_KERNEL_HANDLE. The caller can also optionally set the OBJ_CASE_INSENSITIVE flag, which indicates that name-lookup code should ignore the case of **ObjectName** rather than performing an exact-match search. |

### -param ServerPortCookie

[in, optional] Pointer to context information defined by the minifilter. This information can be used to distinguish among multiple communication server ports that are created by the same minifilter. *FltMgr* passes this context pointer as a parameter to the [**ConnectNotifyCallback**](nc-fltkernel-pflt_connect_notify.md) routine. This parameter is optional and can be NULL.

### -param ConnectNotifyCallback

[in] Pointer to a caller-supplied [**ConnectNotifyCallback**](nc-fltkernel-pflt_connect_notify.md) callback routine. *FltMgr* calls this routine whenever a user-mode application calls [**FilterConnectCommunicationPort**](/windows/win32/api/fltuser/nf-fltuser-filterconnectcommunicationport) to send a connection request to the minifilter. This parameter is required and can't be NULL.

### -param DisconnectNotifyCallback

[in] Pointer to a caller-supplied [**DisconnectNotifyCallback**](nc-fltkernel-pflt_disconnect_notify.md) callback routine. *FltMgr* calls this routine whenever the user-mode handle count for the client port reaches zero or when the minifilter is about to be unloaded. This parameter is required and can't be NULL.

### -param MessageNotifyCallback

[in, optional] Pointer to a caller-supplied [**MessageNotifyCallback**](nc-fltkernel-pflt_message_notify.md) callback routine. *FltMgr* calls this routine whenever a user-mode application calls [**FilterSendMessage**](/windows/win32/api/fltuser/nf-fltuser-filtersendmessage) to send a message to the minifilter through the client port. This parameter is optional and can be NULL. If it is NULL, any request made from user mode to send data to the port receives an error.

### -param MaxConnections

[in] Maximum number of simultaneous client connections to be allowed for this server port. This parameter is required and must be greater than zero.

## -returns

**FltCreateCommunicationPort** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following.

| Return code | Description |
| ----------- | ----------- |
| STATUS_FLT_DELETING_OBJECT | The specified **Filter** is being torn down. This is an error code. |
| STATUS_INSUFFICIENT_RESOURCES | **FltCreateCommunicationPort** encountered a pool allocation failure. This is an error code. |
| STATUS_OBJECT_NAME_COLLISION | A minifilter communication port with the same name already exists. Port names must be unique. This is an error code. |

## -remarks

A minifilter calls **FltCreateCommunicationPort** to create a communication server port object.

After the server port has been created, a user-mode application can connect to the port by calling [**FilterConnectCommunicationPort**](/windows/win32/api/fltuser/nf-fltuser-filterconnectcommunicationport). When connected, the user-mode application can send and receive messages by calling user-mode messaging functions such as [**FilterSendMessage**](/windows/win32/api/fltuser/nf-fltuser-filtersendmessage), [**FilterGetMessage**](/windows/win32/api/fltuser/nf-fltuser-filtergetmessage), and [**FilterReplyMessage**](/windows/win32/api/fltuser/nf-fltuser-filterreplymessage).

Callers must set the OBJ_KERNEL_HANDLE **Attributes** flag for the **ObjectAttributes** parameter of **FltCreateCommunicationPort**. Setting this flag prevents the minifilter communication server port handle from being used by a user-mode process in whose context a caller of **FltCreateCommunicationPort** might be running. If this flag is not set, **FltCreateCommunicationPort** returns STATUS_INVALID_PARAMETER.

Any server port that **FltCreateCommunicationPort** creates must eventually be closed by calling [**FltCloseCommunicationPort**](nf-fltkernel-fltclosecommunicationport.md). When the server port is closed, no new connections to the server port are allowed, and all calls to [**FilterConnectCommunicationPort**](/windows/win32/api/fltuser/nf-fltuser-filterconnectcommunicationport) fail. However, any existing connections remain open until they are closed by the user-mode application or the minifilter, or until the minifilter is unloaded.

For more information, see [Communication between user-mode and minifilters](/windows-hardware/drivers/ifs/communication-between-user-mode-and-kernel-mode).

## -see-also

[**FilterConnectCommunicationPort**](/windows/win32/api/fltuser/nf-fltuser-filterconnectcommunicationport)

[**FilterGetMessage**](/windows/win32/api/fltuser/nf-fltuser-filtergetmessage)

[**FilterReplyMessage**](/windows/win32/api/fltuser/nf-fltuser-filterreplymessage)

[**FilterSendMessage**](/windows/win32/api/fltuser/nf-fltuser-filtersendmessage)

[**FltBuildDefaultSecurityDescriptor**](nf-fltkernel-fltbuilddefaultsecuritydescriptor.md)

[**FltCloseClientPort**](nf-fltkernel-fltcloseclientport.md)

[**FltCloseCommunicationPort**](nf-fltkernel-fltclosecommunicationport.md)

[**FltFreeSecurityDescriptor**](nf-fltkernel-fltfreesecuritydescriptor.md)

[**FltSendMessage**](nf-fltkernel-fltsendmessage.md)

[**InitializeObjectAttributes**](/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes)

[**OBJECT_ATTRIBUTES**](/windows/win32/api/ntdef/ns-ntdef-_object_attributes)

[**PFLT_FILTER_UNLOAD_CALLBACK**](nc-fltkernel-pflt_filter_unload_callback.md)

[**ProbeForRead**](../wdm/nf-wdm-probeforread.md)

[**ProbeForWrite**](../wdm/nf-wdm-probeforwrite.md)

[**SECURITY_DESCRIPTOR**](../ntifs/ns-ntifs-_security_descriptor.md)
