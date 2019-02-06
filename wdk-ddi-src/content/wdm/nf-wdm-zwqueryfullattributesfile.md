---
UID: NF:wdm.ZwQueryFullAttributesFile
title: ZwQueryFullAttributesFile function (wdm.h)
description: The ZwQueryFullAttributesFile routine supplies network open information for the specified file.
old-location: kernel\zwqueryfullattributesfile.htm
tech.root: kernel
ms.assetid: 896ea6aa-54e8-4109-8597-58d8d2cd75ce
ms.date: 04/30/2018
ms.keywords: NtQueryFullAttributesFile, ZwQueryFullAttributesFile, ZwQueryFullAttributesFile routine [Kernel-Mode Driver Architecture], k111_58eefadc-2aff-4252-82a6-6f0c9ab43a19.xml, kernel.zwqueryfullattributesfile, wdm/NtQueryFullAttributesFile, wdm/ZwQueryFullAttributesFile
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ZwQueryFullAttributesFile
-	NtQueryFullAttributesFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# ZwQueryFullAttributesFile function


## -description


The <b>ZwQueryFullAttributesFile</b> routine supplies network open information for the specified file.


## -parameters




### -param ObjectAttributes [in]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a> structure that supplies the attributes to be used for the file object. 


### -param FileInformation [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff545822">FILE_NETWORK_OPEN_INFORMATION</a> structure that receives the returned file attributes information. 


## -returns



<b>ZwQueryFullAttributesFile</b> returns STATUS_SUCCESS on success, or the appropriate error status.




## -remarks



Callers of <b>ZwQueryFullAttributesFile</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://msdn.microsoft.com/0578df31-1467-4bad-ba62-081d61278deb">with special kernel APCs enabled</a>.

<b>NtQueryFullAttributesFile</b> and <b>ZwQueryFullAttributesFile</b> are two versions of the same Windows Native System Services routine. The <b>NtQueryFullAttributesFile</b> routine in the Windows kernel is not directly accessible to kernel-mode drivers. However, kernel-mode drivers can access this routine indirectly by calling the <b>ZwQueryFullAttributesFile</b> routine. 

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545822">FILE_NETWORK_OPEN_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
 

 

