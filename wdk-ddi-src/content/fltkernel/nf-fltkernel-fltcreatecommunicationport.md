---
UID: NF:fltkernel.FltCreateCommunicationPort
title: FltCreateCommunicationPort function
author: windows-driver-content
description: FltCreateCommunicationPort creates a communication server port on which a minifilter driver can receive connection requests from user-mode applications.
old-location: ifsk\fltcreatecommunicationport.htm
old-project: ifsk
ms.assetid: 9987ed6b-7792-4035-9640-9ee9595e854a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_a_to_d_77aa523f-3374-41e7-9b9f-ed0d9e5b3094.xml, FltCreateCommunicationPort, FltCreateCommunicationPort function [Installable File System Drivers], fltkernel/FltCreateCommunicationPort, ifsk.fltcreatecommunicationport
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltCreateCommunicationPort
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltCreateCommunicationPort function


## -description


<b>FltCreateCommunicationPort</b> creates a communication server port on which a minifilter driver can receive connection requests from user-mode applications. 


## -syntax


````
NTSTATUS FltCreateCommunicationPort(
  _In_     PFLT_FILTER            Filter,
  _Out_    PFLT_PORT              *ServerPort,
  _In_     POBJECT_ATTRIBUTES     ObjectAttributes,
  _In_opt_ PVOID                  ServerPortCookie,
  _In_     PFLT_CONNECT_NOTIFY    ConnectNotifyCallback,
  _In_     PFLT_DISCONNECT_NOTIFY DisconnectNotifyCallback,
  _In_opt_ PFLT_MESSAGE_NOTIFY    MessageNotifyCallback,
  _In_     LONG                   MaxConnections
);
````


## -parameters




### -param Filter [in]

Opaque filter pointer for the caller. 


### -param ServerPort [out]

Pointer to a caller-allocated variable that receives an opaque port handle for the communication server port. The minifilter driver uses this handle to listen for incoming connection requests from a user-mode application. 


### -param ObjectAttributes [in]

Pointer to an <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> structure that specifies the attributes of the communication server port. This structure must have been initialized by a previous call to <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>. This parameter is required and cannot be <b>NULL</b>. Members of this structure for a communication port object include the following. 

<table>
<tr>
<th>Member</th>
<th>Value</th>
</tr>
<tr>
<td>
<b>ULONG </b><b>Length</b>

</td>
<td>

<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a> sets this member to <b>sizeof(</b>OBJECT_ATTRIBUTES<b>)</b>.

</td>
</tr>
<tr>
<td>
<b>PUNICODE_STRING </b><b>ObjectName</b>

</td>
<td>
Pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure containing a unique name (for example, L"\\MyFilterPort") for the port object. 

</td>
</tr>
<tr>
<td>
<b>PSECURITY_DESCRIPTOR </b><b>SecurityDescriptor</b>

</td>
<td>
Pointer to a security descriptor (<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>) to be applied to the port object. If needed, a default security descriptor can be created by calling <a href="..\fltkernel\nf-fltkernel-fltbuilddefaultsecuritydescriptor.md">FltBuildDefaultSecurityDescriptor</a>. 

</td>
</tr>
<tr>
<td>
<b>ULONG </b><b>Attributes</b>

</td>
<td>
Bitmask of flags specifying the desired attributes for the port handle. These flags must include OBJ_KERNEL_HANDLE. The caller can also optionally set the OBJ_CASE_INSENSITIVE flag, which indicates that name-lookup code should ignore the case of <b>ObjectName</b> rather than performing an exact-match search. 

</td>
</tr>
</table>
 


### -param ServerPortCookie [in, optional]

Pointer to context information defined by the minifilter driver. This information can be used to distinguish among multiple communication server ports that are created by the same minifilter driver. The Filter Manager passes this context pointer as a parameter to the <i>ConnectNotifyCallback</i> routine. This parameter is optional and can be <b>NULL</b>. 


### -param ConnectNotifyCallback [in]

Pointer to a caller-supplied callback routine. The Filter Manager calls this routine whenever a user-mode application calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff540460">FilterConnectCommunicationPort</a> to send a connection request to the minifilter driver. This parameter is required and cannot be <b>NULL</b>. This routine is called at IRQL = PASSIVE_LEVEL. 

This routine is declared as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef NTSTATUS
(*PFLT_CONNECT_NOTIFY) (
      IN PFLT_PORT ClientPort,
      IN PVOID ServerPortCookie,
      IN PVOID ConnectionContext,
      IN ULONG SizeOfContext,
      OUT PVOID *ConnectionPortCookie
      );</pre>
</td>
</tr>
</table></span></div>




#### ClientPort

Opaque handle for the new client port that is established between the user-mode application and the kernel-mode minifilter driver. 

The minifilter driver must pass this handle as the <i>ClientPort</i> parameter to <a href="..\fltkernel\nf-fltkernel-fltsendmessage.md">FltSendMessage</a> when sending and replying to messages on this client port. (Note that this is not the same as the <i>ServerPort</i> handle returned by <b>FltCreateCommunicationPort</b>.) 

The minifilter driver must eventually close this client port. The client port is closed by calling <a href="..\fltkernel\nf-fltkernel-fltcloseclientport.md">FltCloseClientPort</a>, usually from the minifilter driver's <i>DisconnectNotifyCallback</i> routine. 



#### ServerPortCookie

Pointer to context information defined by the minifilter driver. This information can be used to distinguish among multiple communication server ports that are created by the same minifilter driver. When the server port was created, the minifilter driver passed this context pointer as a parameter to <b>FltCreateCommunicationPort</b>. 



#### ConnectionContext

Context information pointer that the user-mode application passed in the <i>lpContext</i> parameter to <b>FilterConnectCommunicationPort</b>. 



#### SizeOfContext

Size, in bytes, of the buffer that <i>ConnectionContext </i>points to. 



#### ConnectionPortCookie

Pointer to information that uniquely identifies this client port. This information is defined by the minifilter driver. The Filter Manager passes this context pointer as a parameter to the minifilter driver's <i>DisconnectNotifyCallback</i> and <i>MessageNotifyCallback</i> routines. 


### -param DisconnectNotifyCallback [in]

Pointer to a caller-supplied callback routine to be called whenever the user-mode handle count for the client port reaches zero or when the minifilter driver is about to be unloaded. This parameter is required and cannot be <b>NULL</b>. This routine is called at IRQL = PASSIVE_LEVEL. 

This routine is declared as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef VOID
(*PFLT_DISCONNECT_NOTIFY) (
      IN PVOID ConnectionCookie
      );</pre>
</td>
</tr>
</table></span></div>




#### ConnectionCookie

Pointer to information that uniquely identifies this client port. This information is defined by the minifilter driver. When the client port was created, the minifilter driver returned this context pointer in the <i>ConnectionPortCookie</i> parameter of its <i>ConnectNotifyCallback</i> routine. 


### -param MessageNotifyCallback [in, optional]

Pointer to a caller-supplied callback routine. The Filter Manager calls this routine, at IRQL = PASSIVE_LEVEL, whenever a user-mode application calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff541513">FilterSendMessage</a> to send a message to the minifilter driver through the client port. This parameter is optional and can be <b>NULL</b>. If it is <b>NULL</b>, any request made from user mode to send data to the port will receive an error. 

This routine is declared as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef NTSTATUS
(*PFLT_MESSAGE_NOTIFY) (
      IN PVOID PortCookie,
      IN PVOID InputBuffer OPTIONAL,
      IN ULONG InputBufferLength,
      OUT PVOID OutputBuffer OPTIONAL,
      IN ULONG OutputBufferLength,
      OUT PULONG ReturnOutputBufferLength
      );</pre>
</td>
</tr>
</table></span></div>




#### PortCookie

Pointer to information that uniquely identifies this client port. This information is defined by the minifilter driver. When the client port was created, the minifilter driver returned this context pointer in the <i>ConnectionPortCookie</i> parameter of its <i>ConnectNotifyCallback</i> routine. 



#### InputBuffer

Pointer to a caller-allocated buffer containing the message to be sent to the minifilter driver. 

Note that <i>InputBuffer</i> is a pointer to a raw, unlocked user-mode buffer. This pointer is valid only in the context of the user-mode process and must only be accessed from within a <b>try</b>/<b>except</b> block. 

The filter manager calls <a href="..\wdm\nf-wdm-probeforread.md">ProbeForRead</a> to validate this pointer, but it does not ensure that the buffer is properly aligned. If the buffer contains structures that have alignment requirements, the minifilter driver is responsible for performing any necessary alignment checks. To do this, the minifilter driver can use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549486">IS_ALIGNED</a> macro as shown in the MiniSpy sample minifilter driver. 

This parameter is optional and can be <b>NULL</b>. 



#### InputBufferLength

Size, in bytes, of the buffer that <i>InputBuffer </i>points to. This parameter is ignored if <i>InputBuffer</i> is <b>NULL</b>. 



#### OutputBuffer

Pointer to a caller-allocated buffer that receives the reply (if any) from the minifilter driver. 

Note that <i>OutputBuffer</i> is a pointer to a raw, unlocked user-mode buffer. This pointer is valid only in the context of the user-mode process and must only be accessed from within a <b>try</b>/<b>except</b> block. 

The filter manager calls <a href="..\wdm\nf-wdm-probeforwrite.md">ProbeForWrite</a> to validate this pointer, but it does not ensure that the buffer is properly aligned. If the buffer contains structures that have alignment requirements, the minifilter driver is responsible for performing any necessary alignment checks. To do this, the minifilter driver can use the <b>IS_ALIGNED</b> macro as shown in the MiniSpy sample minifilter driver.

This parameter is optional and can be <b>NULL</b>. 



#### OutputBufferLength

Size, in bytes, of the buffer that <i>OutputBuffer </i>points to. This parameter is ignored if <i>OutputBuffer</i> is <b>NULL</b>. 



#### ReturnOutputBufferLength

Pointer to a caller-allocated variable that receives the number of bytes returned in the buffer that <i>OutputBuffer</i> points to. 


### -param MaxConnections [in]

Maximum number of simultaneous client connections to be allowed for this server port. This parameter is required and must be greater than zero. 


## -returns



<b>FltCreateCommunicationPort</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>Filter</i> is being torn down. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>FltCreateCommunicationPort</b> encountered a pool allocation failure. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_COLLISION</b></dt>
</dl>
</td>
<td width="60%">
A minifilter driver communication port with the same name already exists. Port names must be unique. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



A minifilter driver calls <b>FltCreateCommunicationPort</b> to create a communication server port object. 

After the server port has been created, a user-mode application can connect to the port by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff540460">FilterConnectCommunicationPort</a>. When connected, the user-mode application can send and receive messages by calling user-mode messaging functions such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff541513">FilterSendMessage</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff540506">FilterGetMessage</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff541508">FilterReplyMessage</a>. 

Callers must set the OBJ_KERNEL_HANDLE <b>Attributes</b> flag for the <i>ObjectAttributes</i> parameter of <b>FltCreateCommunicationPort</b>. Setting this flag prevents the minifilter driver communication server port handle from being used by a user-mode process in whose context a caller of <b>FltCreateCommunicationPort</b> might be running. If this flag is not set, <b>FltCreateCommunicationPort</b> returns STATUS_INVALID_PARAMETER. 

Any server port that is created by <b>FltCreateCommunicationPort</b> must eventually be closed by calling <a href="..\fltkernel\nf-fltkernel-fltclosecommunicationport.md">FltCloseCommunicationPort</a>. When the server port is closed, no new connections to the server port are allowed, and all calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff540460">FilterConnectCommunicationPort</a> fail. However, any existing connections remain open until they are closed by the user-mode application or the minifilter driver, or until the minifilter driver is unloaded. 




## -see-also

<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>



<a href="..\fltkernel\nf-fltkernel-fltbuilddefaultsecuritydescriptor.md">FltBuildDefaultSecurityDescriptor</a>



<a href="..\fltkernel\nf-fltkernel-fltsendmessage.md">FltSendMessage</a>



<a href="..\wdm\nf-wdm-probeforread.md">ProbeForRead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540506">FilterGetMessage</a>



<a href="..\fltkernel\nc-fltkernel-pflt_filter_unload_callback.md">PFLT_FILTER_UNLOAD_CALLBACK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540460">FilterConnectCommunicationPort</a>



<a href="..\fltkernel\nf-fltkernel-fltclosecommunicationport.md">FltCloseCommunicationPort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541513">FilterSendMessage</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541508">FilterReplyMessage</a>



<a href="..\fltkernel\nf-fltkernel-fltfreesecuritydescriptor.md">FltFreeSecurityDescriptor</a>



<a href="..\fltkernel\nf-fltkernel-fltcloseclientport.md">FltCloseClientPort</a>



<a href="..\wdm\nf-wdm-probeforwrite.md">ProbeForWrite</a>



<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>



<a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a>



 

 


