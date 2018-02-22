---
UID: NS:fltkernel._FLT_REGISTRATION
title: "_FLT_REGISTRATION"
author: windows-driver-content
description: The FLT_REGISTRATION structure is passed as a parameter to FltRegisterFilter.
old-location: ifsk\flt_registration.htm
old-project: ifsk
ms.assetid: 3313af42-0e0a-4ad0-b0bb-0afb795e24fd
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: fltkernel/FLT_REGISTRATION, FLT_REGISTRATION, FltSystemStructures_5257e153-faae-4eb8-845a-f6c137a29390.xml, FLTFL_REGISTRATION_SUPPORT_NPFS_MSFS, fltkernel/PFLT_REGISTRATION, ifsk.flt_registration, FLTFL_REGISTRATION_DO_NOT_SUPPORT_SERVICE_STOP, *PFLT_REGISTRATION, FLT_REGISTRATION structure [Installable File System Drivers], PFLT_REGISTRATION structure pointer [Installable File System Drivers], _FLT_REGISTRATION, PFLT_REGISTRATION, FLTFL_REGISTRATION_SUPPORT_DAX_VOLUME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	fltkernel.h
apiname:
-	FLT_REGISTRATION
product: Windows
targetos: Windows
req.typenames: FLT_REGISTRATION, *PFLT_REGISTRATION
---

# _FLT_REGISTRATION structure


## -description


The FLT_REGISTRATION structure is passed as a parameter to <a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>. 


## -syntax


````
typedef struct _FLT_REGISTRATION {
  USHORT                                      Size;
  USHORT                                      Version;
  FLT_REGISTRATION_FLAGS                      Flags;
  const FLT_CONTEXT_REGISTRATION              *ContextRegistration;
  const FLT_OPERATION_REGISTRATION            *OperationRegistration;
  PFLT_FILTER_UNLOAD_CALLBACK                 FilterUnloadCallback;
  PFLT_INSTANCE_SETUP_CALLBACK                InstanceSetupCallback;
  PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK       InstanceQueryTeardownCallback;
  PFLT_INSTANCE_TEARDOWN_CALLBACK             InstanceTeardownStartCallback;
  PFLT_INSTANCE_TEARDOWN_CALLBACK             InstanceTeardownCompleteCallback;
  PFLT_GENERATE_FILE_NAME                     GenerateFileNameCallback;
  PFLT_NORMALIZE_NAME_COMPONENT               NormalizeNameComponentCallback;
  PFLT_NORMALIZE_CONTEXT_CLEANUP              NormalizeContextCleanupCallback;
#if FLT_MGR_LONGHORN
  PFLT_TRANSACTION_NOTIFICATION_CALLBACK      TransactionNotificationCallback;
  PFLT_NORMALIZE_NAME_COMPONENT_EX            NormalizeNameComponentExCallback;
#endif 
#ifdef FLT_MFG_WIN8
  PFLT_SECTION_CONFLICT_NOTIFICATION_CALLBACK SectionNotificationCallback;
#endif 
} FLT_REGISTRATION, *PFLT_REGISTRATION;
````


## -struct-fields




### -field Size

The size, in bytes, of the FLT_REGISTRATION structure. Minifilter drivers must set this member to <b>sizeof</b>(FLT_REGISTRATION). 


### -field Version

The revision level of the FLT_REGISTRATION structure. Minifilter drivers must set this member to FLT_REGISTRATION_VERSION. 


### -field Flags

A bitmask of minifilter registration flags. This member can be <b>NULL</b> or a combination of the following. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="FLTFL_REGISTRATION_DO_NOT_SUPPORT_SERVICE_STOP"></a><a id="fltfl_registration_do_not_support_service_stop"></a><dl>
<dt><b>FLTFL_REGISTRATION_DO_NOT_SUPPORT_SERVICE_STOP</b></dt>
</dl>
</td>
<td width="60%">
If this flag is set, the minifilter is not unloaded in response to service stop requests, even if the <b>FilterUnloadCallback</b> member is not <b>NULL</b>. 

</td>
</tr>
<tr>
<td width="40%"><a id="FLTFL_REGISTRATION_SUPPORT_NPFS_MSFS"></a><a id="fltfl_registration_support_npfs_msfs"></a><dl>
<dt><b>FLTFL_REGISTRATION_SUPPORT_NPFS_MSFS</b></dt>
</dl>
</td>
<td width="60%">
If this flag is set,  the minifilter will support filtering of named pipe and mailslot requests.

</td>
</tr>
<tr>
<td width="40%"><a id="FLTFL_REGISTRATION_SUPPORT_DAX_VOLUME"></a><a id="fltfl_registration_support_dax_volume"></a><dl>
<dt><b>FLTFL_REGISTRATION_SUPPORT_DAX_VOLUME</b></dt>
</dl>
</td>
<td width="60%">
If this flag is set, the minifilter will support attaching to a direct access (DAX) volume. This will indicate to Filter Manager that the minifilter will filter the DAX volume. This flag was introduced in Windows 10, version 1607.

</td>
</tr>
</table>
 


### -field ContextRegistration

 A variable-length array of <a href="..\fltkernel\ns-fltkernel-_flt_context_registration.md">FLT_CONTEXT_REGISTRATION</a> structures, one for each context type that the minifilter uses. The last element in the array must be {FLT_CONTEXT_END}. 


### -field OperationRegistration

A variable-length array of <a href="..\fltkernel\ns-fltkernel-_flt_operation_registration.md">FLT_OPERATION_REGISTRATION</a> structures, one for each type of I/O for which the minifilter registers preoperation (<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>) and postoperation (<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>) callback routines. The last element in the array must be {IRP_MJ_OPERATION_END}. 


### -field FilterUnloadCallback

A pointer to a routine of type <a href="..\fltkernel\nc-fltkernel-pflt_filter_unload_callback.md">PFLT_FILTER_UNLOAD_CALLBACK</a> to be registered as the minifilter's <i>FilterUnloadCallback</i> routine. This member is optional and can be <b>NULL</b>. 


### -field InstanceSetupCallback

A pointer to a routine of type <a href="..\fltkernel\nc-fltkernel-pflt_instance_setup_callback.md">PFLT_INSTANCE_SETUP_CALLBACK</a> to be registered as the minifilter's <i>InstanceSetupCallback</i> routine. This member is optional and can be <b>NULL</b>. 


### -field InstanceQueryTeardownCallback

A pointer to a routine of type <a href="..\fltkernel\nc-fltkernel-pflt_instance_query_teardown_callback.md">PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK</a> to be registered as the minifilter's <i>InstanceQueryTeardownCallback</i> routine. This member is optional and can be <b>NULL</b>. 


### -field InstanceTeardownStartCallback

A pointer to a routine of type <a href="..\fltkernel\nc-fltkernel-pflt_instance_teardown_callback.md">PFLT_INSTANCE_TEARDOWN_CALLBACK</a> to be registered as the minifilter's <i>InstanceTeardownStartCallback</i> routine. This member is optional and can be <b>NULL</b>. 


### -field InstanceTeardownCompleteCallback

A pointer to a routine of type <a href="..\fltkernel\nc-fltkernel-pflt_instance_teardown_callback.md">PFLT_INSTANCE_TEARDOWN_CALLBACK</a> to be registered as the minifilter's <i>InstanceTeardownCompleteCallback</i> routine. This member is optional and can be <b>NULL</b>. 


### -field GenerateFileNameCallback

A pointer to a routine of type <a href="..\fltkernel\nc-fltkernel-pflt_generate_file_name.md">PFLT_GENERATE_FILE_NAME</a> to be registered as the minifilter's <i>GenerateFileNameCallback</i> routine. This member is optional and can be <b>NULL</b>. 


### -field NormalizeNameComponentCallback

A pointer to a routine of type <a href="..\fltkernel\nc-fltkernel-pflt_normalize_name_component.md">PFLT_NORMALIZE_NAME_COMPONENT</a> to be registered as the minifilter's <i>NormalizeNameComponentCallback</i> routine. This member is optional and can be <b>NULL</b>. 


### -field NormalizeContextCleanupCallback

A pointer to a routine of type <a href="..\fltkernel\nc-fltkernel-pflt_normalize_context_cleanup.md">PFLT_NORMALIZE_CONTEXT_CLEANUP</a> to be registered as the minifilter's <i>NormalizeContextCleanupCallback</i> routine. This member is optional and can be <b>NULL</b>. 


### -field TransactionNotificationCallback

(Windows Vista and later only.)  A pointer to a routine of type <a href="..\fltkernel\nc-fltkernel-pflt_transaction_notification_callback.md">PFLT_TRANSACTION_NOTIFICATION_CALLBACK</a> to be registered as the minifilter's <i>TransactionNotificationCallback</i> routine. This member is optional and can be <b>NULL</b>. 


### -field NormalizeNameComponentExCallback

(Windows Vista and later only.)   A pointer to a routine of type <a href="..\fltkernel\nc-fltkernel-pflt_normalize_name_component_ex.md">PFLT_NORMALIZE_NAME_COMPONENT_EX</a> to be registered as the minifilter driver's <i>NormalizeNameComponentExCallback</i> routine. This member is optional and can be <b>NULL</b>.  

Compared to the <i>NormalizeNameComponentCallback</i> callback routine, the <i>NormalizeNameComponentExCallback</i> callback routine supports an additional file object parameter,   <i> FileObject</i> (of type PFILE_OBJECT). A minifilter driver can use this parameter to acquire additional information, such as that provided by the <a href="..\ntddk\ns-ntddk-_txn_parameter_block.md">TXN_PARAMETER_BLOCK</a> structure.

A minifilter driver can simultaneously set both the <i>NormalizeNameComponentCallback</i> and <i>NormalizeNameComponentExCallback</i> members to <b>NULL</b>; however, a name provider minifilter driver must register either a <i>NormalizeNameComponentCallback</i> or <i>NormalizeNameComponentExCallback</i> callback routine, or both.  For example, a name provider minifilter driver that has no use for the additional <i>FileObject</i> parameter can set the <i>NormalizeNameComponentExCallback</i> member to <b>NULL</b> and only provide a <i>NormalizeNameComponentCallback</i> callback routine.

A minifilter driver can provide both a <i>NormalizeNameComponentCallback</i> callback and a <i>NormalizeNameComponentExCallback</i> callback.  In this case, starting with Windows Vista, the filter manager will use only the <i>NormalizeNameComponentExCallback</i> callback; for Windows operating systems prior to Windows Vista, the filter manager will  use only the <i>NormalizeNameComponentCallback</i> callback. This allows the same minifilter driver binary to run under all versions of the operating system.


### -field SectionNotificationCallback

Pointer to a routine of type <a href="..\fltkernel\nc-fltkernel-pflt_section_conflict_notification_callback.md">PFLT_SECTION_CONFLICT_NOTIFICATION_CALLBACK</a> to be registered as the minifilter's <i>SectionNotificationCallback</i> routine. This member is optional and can be <b>NULL</b>. This callback is called for notifications of I/O failures for sections created with <a href="..\fltkernel\nf-fltkernel-fltcreatesectionfordatascan.md">FltCreateSectionForDatascan</a>.


## -remarks



The FLT_REGISTRATION structure is used to provide information about a file system minifilter, such as a <i>FilterUnloadCallback</i> (<a href="..\fltkernel\nc-fltkernel-pflt_filter_unload_callback.md">PFLT_FILTER_UNLOAD_CALLBACK</a>) routine and preoperation (<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>) and postoperation (<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>) callback routines, to the filter manager. The minifilter passes a pointer to this structure as the <i>Registration</i> parameter to <a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>



<a href="..\fltkernel\ns-fltkernel-_flt_operation_registration.md">FLT_OPERATION_REGISTRATION</a>



<a href="..\fltkernel\nc-fltkernel-pflt_instance_teardown_callback.md">PFLT_INSTANCE_TEARDOWN_CALLBACK</a>



<a href="..\fltkernel\nc-fltkernel-pflt_normalize_name_component.md">PFLT_NORMALIZE_NAME_COMPONENT</a>



<a href="..\fltkernel\nc-fltkernel-pflt_transaction_notification_callback.md">PFLT_TRANSACTION_NOTIFICATION_CALLBACK</a>



<a href="..\fltkernel\ns-fltkernel-_flt_context_registration.md">FLT_CONTEXT_REGISTRATION</a>



<a href="..\fltkernel\nc-fltkernel-pflt_instance_setup_callback.md">PFLT_INSTANCE_SETUP_CALLBACK</a>



<a href="..\fltkernel\nc-fltkernel-pflt_generate_file_name.md">PFLT_GENERATE_FILE_NAME</a>



<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>



<a href="..\fltkernel\nc-fltkernel-pflt_normalize_name_component_ex.md">PFLT_NORMALIZE_NAME_COMPONENT_EX</a>



<a href="..\fltkernel\nc-fltkernel-pflt_normalize_context_cleanup.md">PFLT_NORMALIZE_CONTEXT_CLEANUP</a>



<a href="..\fltkernel\nc-fltkernel-pflt_instance_query_teardown_callback.md">PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK</a>



<a href="..\fltkernel\nc-fltkernel-pflt_filter_unload_callback.md">PFLT_FILTER_UNLOAD_CALLBACK</a>



<a href="..\fltkernel\nc-fltkernel-pflt_normalize_context_cleanup.md">PFLT_NORMALIZE_CONTEXT_CLEANUP</a>



<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FLT_REGISTRATION structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

