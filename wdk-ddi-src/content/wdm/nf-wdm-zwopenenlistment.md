---
UID: NF:wdm.ZwOpenEnlistment
title: ZwOpenEnlistment function
author: windows-driver-content
description: The ZwOpenEnlistment routine obtains a handle to an existing enlistment object.
old-location: kernel\zwopenenlistment.htm
old-project: kernel
ms.assetid: b70d524f-2341-4b19-9c4a-f5095cb7f412
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: NtOpenEnlistment, ZwOpenEnlistment, ZwOpenEnlistment routine [Kernel-Mode Driver Architecture], kernel.zwopenenlistment, ktm_ref_cc7719f5-a9a2-42be-9961-01f910f864bc.xml, wdm/NtOpenEnlistment, wdm/ZwOpenEnlistment
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ZwOpenEnlistment
-	NtOpenEnlistment
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ZwOpenEnlistment function


## -description


The <b>ZwOpenEnlistment</b> routine obtains a handle to an existing <a href="https://msdn.microsoft.com/80e61475-4bb7-4eaa-b9f1-ff95eac9bc77">enlistment object</a>.


## -syntax


````
NTSTATUS ZwOpenEnlistment(
  _Out_    PHANDLE            EnlistmentHandle,
  _In_     ACCESS_MASK        DesiredAccess,
  _In_     HANDLE             RmHandle,
  _In_     LPGUID             EnlistmentGuid,
  _In_opt_ POBJECT_ATTRIBUTES ObjectAttributes
);
````


## -parameters




### -param EnlistmentHandle [out]

A pointer to a caller-allocated variable that receives a handle to an enlistment object if the call to <b>ZwOpenEnlistment</b> succeeds.


### -param DesiredAccess [in]

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>-typed value that specifies the requested access to the enlistment object. For more information about how to specify this parameter, see the <i>DesiredAccess</i> parameter of <a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a>. This parameter cannot be zero.


#### - RmHandle [in]

A handle to a resource manager object that was obtained by a previous call to <a href="..\wdm\nf-wdm-zwcreateresourcemanager.md">ZwCreateResourceManager</a> or <a href="..\wdm\nf-wdm-zwopenresourcemanager.md">ZwOpenResourceManager</a>.


### -param EnlistmentGuid [in]

A pointer to a GUID that identifies the enlistment. For more information, see the following Remarks section.


### -param ObjectAttributes [in, optional]

A pointer to an <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> structure that specifies the object's attributes. Use the <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a> routine to initialize this structure, but specify only that routine's <i>InitializedAttributes</i> and <i>Attributes</i> parameters. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE flag in the <i>Attributes</i> parameter. This parameter is optional and can be <b>NULL</b>. 


## -returns



<b>ZwOpenEnlistment</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The object handle is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The caller does not have appropriate access to the enlistment object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>DesiredAccess</i> parameter's value is zero, or the <i>EnlistmentGuid</i> parameter's value is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ENLISTMENT_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The enlistment that the <i>EnlistmentGuid</i> parameter specifies does not exist for the resource manager that the <i>RmHandle </i>parameter specifies.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The value of the <i>DesiredAccess</i> parameter is invalid.

</td>
</tr>
</table>
 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



Typically, a TPS component calls <b>ZwOpenEnlistment</b> after it receives an enlistment GUID from another TPS component that had previously called <a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a>. Most TPS designs do not require calling <b>ZwOpenEnlistment</b>.

A resource manager that calls <b>ZwOpenEnlistment</b> must eventually call <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a> to close the object handle.

For more information about <b>ZwOpenEnlistment</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544266">Enlistment Objects</a>.

<b>NtOpenEnlistment</b> and <b>ZwOpenEnlistment</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also

<a href="..\wdm\nf-wdm-zwsetinformationenlistment.md">ZwSetInformationEnlistment</a>



<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>



<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>



<a href="..\wdm\nf-wdm-zwcreateresourcemanager.md">ZwCreateResourceManager</a>



<a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a>



<a href="..\wdm\nf-wdm-zwqueryinformationenlistment.md">ZwQueryInformationEnlistment</a>



<a href="..\wdm\nf-wdm-zwopenresourcemanager.md">ZwOpenResourceManager</a>



<a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwOpenEnlistment routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

