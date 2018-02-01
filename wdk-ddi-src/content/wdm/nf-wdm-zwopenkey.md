---
UID: NF:wdm.ZwOpenKey
title: ZwOpenKey function
author: windows-driver-content
description: The ZwOpenKey routine opens an existing registry key.
old-location: kernel\zwopenkey.htm
old-project: kernel
ms.assetid: e92f0297-8bfc-496d-a00b-e7b5711c7856
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k111_8583b145-a6be-4e4f-8e46-ca7d48b8a07f.xml, ZwOpenKey routine [Kernel-Mode Driver Architecture], kernel.zwopenkey, wdm/ZwOpenKey, ZwOpenKey
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlZwPassive, PowerIrpDDis, ZwRegistryOpen, HwStorPortProhibitedDDIs, ZwRegistryCreate, ZwRegistryOpen(storport)
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
-	ZwOpenKey
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ZwOpenKey function


## -description


The <b>ZwOpenKey</b> routine opens an existing registry key. 


## -syntax


````
NTSTATUS ZwOpenKey(
  _Out_ PHANDLE            KeyHandle,
  _In_  ACCESS_MASK        DesiredAccess,
  _In_  POBJECT_ATTRIBUTES ObjectAttributes
);
````


## -parameters




### -param KeyHandle [out]

Pointer to the HANDLE variable that receives the handle to the key.


### -param DesiredAccess [in]

Specifies an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that determines the requested access to the object. For more information, see the <i>DesiredAccess</i> parameter of <a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a>. 


### -param ObjectAttributes [in]

Pointer to an <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> structure that specifies the object name and other attributes. Use <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a> to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>. 


## -returns


<b>ZwOpenKey</b> returns STATUS_SUCCESS if the given key was opened. Otherwise, it can return an error status, including the following:



## -remarks


<b>ZwOpenKey</b> supplies a handle that the caller can use to manipulate a registry key. The routine provides a subset of the functionality of <a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565537">Using the Registry in a Driver</a>.

If the specified key does not exist, <b>ZwOpenKey</b> returns an error status and does not return a key handle.

Once the handle pointed to by <i>KeyHandle</i> is no longer in use, the driver must call <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a> to close it.

<b>ZwOpenKey</b> ignores the security information in the structure that the <i>ObjectAttributes</i> parameter points to.

If the caller is not running in a system thread context, it must ensure that any handles it creates are private handles. Otherwise, the handle can be accessed by the process in whose context the driver is running. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557758">Object Handles</a>.

For more information about working with registry keys, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565537">Using the Registry in a Driver</a>.
<div class="alert"><b>Note</b>    If the call to this function occurs in user mode, you should use the name "<b>NtOpenKey</b>" instead of "<b>ZwOpenKey</b>".</div><div> </div>


## -see-also

<a href="..\wdm\nf-wdm-zwenumeratevaluekey.md">ZwEnumerateValueKey</a>

<a href="..\wdm\nf-wdm-zwqueryvaluekey.md">ZwQueryValueKey</a>

<a href="..\wdm\nf-wdm-zwquerykey.md">ZwQueryKey</a>

<a href="..\wdm\nf-wdm-zwsetvaluekey.md">ZwSetValueKey</a>

<a href="..\wdm\nf-wdm-zwflushkey.md">ZwFlushKey</a>

<a href="..\wdm\nf-wdm-zwdeletekey.md">ZwDeleteKey</a>

<a href="..\wdm\nf-wdm-zwenumeratekey.md">ZwEnumerateKey</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>

<a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a>

<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwOpenKey routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

