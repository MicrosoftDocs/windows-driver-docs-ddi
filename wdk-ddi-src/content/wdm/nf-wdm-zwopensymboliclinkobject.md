---
UID: NF:wdm.ZwOpenSymbolicLinkObject
title: ZwOpenSymbolicLinkObject function
author: windows-driver-content
description: The ZwOpenSymbolicLinkObject routine opens an existing symbolic link.
old-location: kernel\zwopensymboliclinkobject.htm
old-project: kernel
ms.assetid: 1b5b9410-1243-4fd4-b02a-fc262abf18c7
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: NtOpenSymbolicLinkObject, ZwOpenSymbolicLinkObject, ZwOpenSymbolicLinkObject routine [Kernel-Mode Driver Architecture], k111_8f2ddd22-26d2-438f-8335-fcc261735592.xml, kernel.zwopensymboliclinkobject, wdm/NtOpenSymbolicLinkObject, wdm/ZwOpenSymbolicLinkObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ZwOpenSymbolicLinkObject
-	NtOpenSymbolicLinkObject
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ZwOpenSymbolicLinkObject function


## -description


The <b>ZwOpenSymbolicLinkObject</b> routine opens an existing symbolic link.


## -syntax


````
NTSTATUS ZwOpenSymbolicLinkObject(
  _Out_ PHANDLE            LinkHandle,
  _In_  ACCESS_MASK        DesiredAccess,
  _In_  POBJECT_ATTRIBUTES ObjectAttributes
);
````


## -parameters




### -param LinkHandle [out]

Pointer to a HANDLE variable that receives a handle to the symbolic link object.


### -param DesiredAccess [in]

Specifies an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that determines the requested access to the object. The caller usually specified GENERIC_READ, so that the handle can be passed to <a href="..\wdm\nf-wdm-zwquerysymboliclinkobject.md">ZwQuerySymbolicLinkObject</a>. 


### -param ObjectAttributes [in]

Pointer to an <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> structure that specifies the object name and other attributes. Use <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a> to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>. 


## -returns



<b>ZwOpenSymbolicLinkObject</b> returns STATUS_SUCCESS on success or the appropriate error status.




## -remarks



Once the handle pointed to by <i>LinkHandle</i> is no longer in use, the driver must call <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a> to close it.

If the caller is not running in a system thread context, it must ensure that any handles it creates are private handles. Otherwise, the handle can be accessed by the process in whose context the driver is running. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557758">Object Handles</a>. 

<div class="alert"><b>Note</b>  If the call to the <b>ZwOpenSymbolicLinkObject</b> function occurs in user mode, you should use the name "NtOpenSymbolicLinkObject" instead of "<b>ZwOpenSymbolicLinkObject</b>". </div>
<div> </div>
<b>NtOpenSymbolicLinkObject</b> and <b>ZwOpenSymbolicLinkObject</b> are two versions of the same Windows Native System Services routine. The <b>NtOpenSymbolicLinkObject</b> routine in the Windows kernel is not directly accessible to kernel-mode drivers. However, kernel-mode drivers can access this routine indirectly by calling the <b>ZwOpenSymbolicLinkObject</b> routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also

<a href="..\wdm\nf-wdm-zwquerysymboliclinkobject.md">ZwQuerySymbolicLinkObject</a>



<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwOpenSymbolicLinkObject routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

