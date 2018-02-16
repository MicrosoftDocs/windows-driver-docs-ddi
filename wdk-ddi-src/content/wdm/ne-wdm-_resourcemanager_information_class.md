---
UID: NE:wdm._RESOURCEMANAGER_INFORMATION_CLASS
title: "_RESOURCEMANAGER_INFORMATION_CLASS"
author: windows-driver-content
description: The RESOURCEMANAGER_INFORMATION_CLASS enumeration identifies the type of information that the ZwQueryInformationResourceManager routine can retrieve for a resource manager object.
old-location: kernel\resourcemanager_information_class.htm
old-project: kernel
ms.assetid: 5ffaad89-b3c0-4fe6-bc2c-2b1f3b1bcfd2
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/ResourceManagerBasicInformation, ktm_ref_72b34c92-3548-4148-94c2-49f4a66ad4bf.xml, wdm/RESOURCEMANAGER_INFORMATION_CLASS, RESOURCEMANAGER_INFORMATION_CLASS, ResourceManagerBasicInformation, _RESOURCEMANAGER_INFORMATION_CLASS, RESOURCEMANAGER_INFORMATION_CLASS enumeration [Kernel-Mode Driver Architecture], kernel.resourcemanager_information_class, wdm/ResourceManagerCompletionInformation, ResourceManagerCompletionInformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
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
-	Wdm.h
apiname:
-	RESOURCEMANAGER_INFORMATION_CLASS
product: Windows
targetos: Windows
req.typenames: RESOURCEMANAGER_INFORMATION_CLASS
req.product: Windows 10 or later.
---

# _RESOURCEMANAGER_INFORMATION_CLASS enumeration


## -description


The <b>RESOURCEMANAGER_INFORMATION_CLASS</b> enumeration identifies the type of information that the <a href="..\wdm\nf-wdm-zwqueryinformationresourcemanager.md">ZwQueryInformationResourceManager</a> routine can retrieve for a <a href="https://msdn.microsoft.com/b44f2035-ee9f-453b-b12d-89ca36a8b280">resource manager object</a>.


## -syntax


````
typedef enum _RESOURCEMANAGER_INFORMATION_CLASS { 
  ResourceManagerBasicInformation       = 0,
  ResourceManagerCompletionInformation  = 1
} RESOURCEMANAGER_INFORMATION_CLASS;
````


## -enum-fields




### -field ResourceManagerBasicInformation

Information about a resource manager object is stored in a <a href="..\wdm\ns-wdm-_resourcemanager_basic_information.md">RESOURCEMANAGER_BASIC_INFORMATION</a> structure. 


### -field ResourceManagerCompletionInformation

Information about a resource manager object is stored in a <a href="..\wdm\ns-wdm-_resourcemanager_completion_information.md">RESOURCEMANAGER_COMPLETION_INFORMATION</a> structure. 


## -see-also

<a href="..\wdm\ns-wdm-_resourcemanager_basic_information.md">RESOURCEMANAGER_BASIC_INFORMATION</a>



<a href="..\wdm\nf-wdm-zwqueryinformationresourcemanager.md">ZwQueryInformationResourceManager</a>



<a href="..\wdm\ns-wdm-_resourcemanager_completion_information.md">RESOURCEMANAGER_COMPLETION_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RESOURCEMANAGER_INFORMATION_CLASS enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

