---
UID: NF:wdm.ZwOpenSection
title: ZwOpenSection function (wdm.h)
description: The ZwOpenSection routine opens a handle for an existing section object.
old-location: kernel\zwopensection.htm
tech.root: kernel
ms.assetid: c4373f7b-cc88-45da-a140-ead1c6891c11
ms.date: 04/30/2018
ms.keywords: NtOpenSection, ZwOpenSection, ZwOpenSection routine [Kernel-Mode Driver Architecture], k111_51851f81-8825-499b-9e7e-36faa8f53b23.xml, kernel.zwopensection, wdm/NtOpenSection, wdm/ZwOpenSection
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ZwOpenSection
- NtOpenSection
product:
- Windows
targetos: Windows
req.typenames: 
---

# ZwOpenSection function


## -description


The <b>ZwOpenSection</b> routine opens a handle for an existing <a href="https://docs.microsoft.com/windows-hardware/drivers/">section object</a>.


## -parameters




### -param SectionHandle [out]

Pointer to a HANDLE variable that receives a handle to the section object.


### -param DesiredAccess [in]

Specifies an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> value that determines the requested access to the object. For more information, see the <i>DesiredAccess</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-zwcreatesection">ZwCreateSection</a>. 


### -param ObjectAttributes [in]

Pointer to an <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a> structure that specifies the object name and other attributes. Use <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a> to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>. 


## -returns



<b>ZwOpenSection</b> returns STATUS_SUCCESS on success, or the appropriate error code on failure. Possible return values include:




## -remarks



If the section does not exist or the system did not grant the requested access, the operation fails.

Once the handle pointed to by <i>SectionHandle</i> is no longer in use, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntclose">ZwClose</a> to close it.

If the caller is not running in a system thread context, it must ensure that any handles it creates are private handles. Otherwise, the handle can be accessed by the process in whose context the driver is running. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/object-handles">Object Handles</a>.

<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<b>NtOpenSection</b>" instead of "<b>ZwOpenSection</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-zwcreatesection">ZwCreateSection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-zwmapviewofsection">ZwMapViewOfSection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-zwunmapviewofsection">ZwUnmapViewOfSection</a>
 

 

