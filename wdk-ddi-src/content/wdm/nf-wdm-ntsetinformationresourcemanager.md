---
UID: NF:wdm.NtSetInformationResourceManager
title: NtSetInformationResourceManager function
author: windows-driver-content
description: The ZwSetInformationResourceManager routine is not used.
old-location: kernel\zwsetinformationresourcemanager.htm
old-project: kernel
ms.assetid: 0a0d86c7-1d42-4312-a4f9-9b9ea092ebec
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: NtSetInformationResourceManager, function [Kernel-Mode Driver Architecture], kernel.zwsetinformationresourcemanager, ktm_ref_6b15a16a-ffed-4f3e-9ca3-370b85896dc2.xml, wdm/, wdm/NtSetInformationResourceManager
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	ZwSetInformationResourceManager
-	NtSetInformationResourceManager
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# NtSetInformationResourceManager function


## -description


The <b>ZwSetInformationResourceManager</b> routine is not used.


## -syntax


````
void (void);
````


## -parameters




### -param ResourceManagerHandle

TBD


### -param ResourceManagerInformationClass

TBD


### -param ResourceManagerInformation

TBD


### -param ResourceManagerInformationLength

TBD




## -returns



This function does not return a value.




## -remarks



<b>NtSetInformationResourceManager</b> and <b>ZwSetInformationResourceManager</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwSetInformationResourceManager function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

