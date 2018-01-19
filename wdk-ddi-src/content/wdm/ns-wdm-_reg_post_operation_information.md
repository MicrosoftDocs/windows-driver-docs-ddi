---
UID: NS:wdm._REG_POST_OPERATION_INFORMATION
title: _REG_POST_OPERATION_INFORMATION
author: windows-driver-content
description: The REG_POST_OPERATION_INFORMATION structure contains information about a completed registry operation that a RegistryCallback routine can use.
old-location: kernel\reg_post_operation_information.htm
old-project: kernel
ms.assetid: 2266e816-2060-4071-bf9f-319daefbfc50
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _REG_POST_OPERATION_INFORMATION, REG_POST_OPERATION_INFORMATION, *PREG_POST_OPERATION_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available on Microsoft Windows Server 2003 and later versions of the Windows operating system, but some structure members are available only for Windows Vista and later versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: REG_POST_OPERATION_INFORMATION
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.typenames: REG_POST_OPERATION_INFORMATION, *PREG_POST_OPERATION_INFORMATION
req.product: Windows 10 or later.
---

# _REG_POST_OPERATION_INFORMATION structure



## -description
The <b>REG_POST_OPERATION_INFORMATION</b> structure contains information about a completed registry operation that a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine can use.



## -syntax

````
typedef struct _REG_POST_OPERATION_INFORMATION {
  PVOID    Object;
  NTSTATUS Status;
  PVOID    PreInformation;
  NTSTATUS ReturnStatus;
  PVOID    CallContext;
  PVOID    ObjectContext;
  PVOID    Reserved;
} REG_POST_OPERATION_INFORMATION, *PREG_POST_OPERATION_INFORMATION;
````


## -struct-fields

### -field Object

A pointer to the registry key object for which the operation has completed. This member is valid only if the Status member of the structure is set to STATUS_SUCCESS. For more information, see <a href="http://go.microsoft.com/fwlink/p/?linkid=613134">Invalid Key Object Pointers in Registry Notifications</a>.


### -field Status

The NTSTATUS-typed value that the system will return for the registry operation.


### -field PreInformation

A pointer to the structure that contains preprocessing information for the registry operation that has completed. For example, if the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine is processing a <b>RegNtPostQueryValueKey</b> operation, the <b>PreInformation</b> member points to a <a href="..\wdm\ns-wdm-_reg_query_value_key_information.md">REG_QUERY_VALUE_KEY_INFORMATION</a> structure. This member is defined for Windows Vista and later versions of the Windows operating system.


### -field ReturnStatus

A driver-supplied NTSTATUS-typed value. If the driver's <i>RegistryCallback</i> routine returns STATUS_CALLBACK_BYPASS, the operating system uses the <b>ReturnStatus</b> member's value as the status that it returns to the thread that initiated the registry operation. (In such cases, the operating system also copies the <b>ReturnStatus</b> member's value to the <b>Status</b> member.) Otherwise, this member is ignored. This member is defined for Windows Vista and later versions of the Windows operating system.


### -field CallContext

Optional driver-defined context information that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine can supply. This member is defined for Windows Vista and later versions of the Windows operating system.


### -field ObjectContext

A pointer to driver-defined context information that the driver has associated with a registry object by calling <a href="..\wdm\nf-wdm-cmsetcallbackobjectcontext.md">CmSetCallbackObjectContext</a>. This member is defined for Windows Vista and later versions of the Windows operating system.


### -field Reserved

This member is reserved for future use. This member is defined for Windows Vista and later versions of the Windows operating system.


## -remarks
For more information about handling post-notifications, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546907">Handling Notifications</a>.

For more information about registry filtering operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-cmsetcallbackobjectcontext.md">CmSetCallbackObjectContext</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_reg_query_value_key_information.md">REG_QUERY_VALUE_KEY_INFORMATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20REG_POST_OPERATION_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

