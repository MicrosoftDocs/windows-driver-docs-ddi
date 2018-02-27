---
UID: NS:wdm._ENLISTMENT_BASIC_INFORMATION
title: "_ENLISTMENT_BASIC_INFORMATION"
author: windows-driver-content
description: The ENLISTMENT_BASIC_INFORMATION structure contains information about an enlistment object.
old-location: kernel\enlistment_basic_information.htm
old-project: kernel
ms.assetid: 50c989b9-147c-41ea-b933-3a3e8575563e
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PENLISTMENT_BASIC_INFORMATION, ENLISTMENT_BASIC_INFORMATION, ENLISTMENT_BASIC_INFORMATION structure [Kernel-Mode Driver Architecture], PENLISTMENT_BASIC_INFORMATION, PENLISTMENT_BASIC_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _ENLISTMENT_BASIC_INFORMATION, kernel.enlistment_basic_information, ktm_ref_5748a3a5-6a2a-4cf1-a610-2a406161b689.xml, wdm/ENLISTMENT_BASIC_INFORMATION, wdm/PENLISTMENT_BASIC_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	ENLISTMENT_BASIC_INFORMATION
product: Windows
targetos: Windows
req.typenames: ENLISTMENT_BASIC_INFORMATION, *PENLISTMENT_BASIC_INFORMATION
req.product: Windows 10 or later.
---

# _ENLISTMENT_BASIC_INFORMATION structure


## -description


The <b>ENLISTMENT_BASIC_INFORMATION</b> structure contains information about an <a href="https://msdn.microsoft.com/80e61475-4bb7-4eaa-b9f1-ff95eac9bc77">enlistment object</a>.


## -syntax


````
typedef struct _ENLISTMENT_BASIC_INFORMATION {
  GUID EnlistmentId;
  GUID TransactionId;
  GUID ResourceManagerId;
} ENLISTMENT_BASIC_INFORMATION, *PENLISTMENT_BASIC_INFORMATION;
````


## -struct-fields




### -field EnlistmentId

A GUID that KTM has assigned to the enlistment object.


### -field TransactionId

A GUID that KTM has assigned to the transaction object that is associated with the enlistment object that the <b>EnlistmentId</b> member identifies.


### -field ResourceManagerId

A GUID that KTM has assigned to the resource manager that created the enlistment.


## -remarks



The <b>ENLISTMENT_BASIC INFORMATION</b> structure is used with the <a href="..\wdm\nf-wdm-zwqueryinformationenlistment.md">ZwQueryInformationEnlistment</a> routine.




## -see-also

<a href="..\wdm\nf-wdm-zwqueryinformationenlistment.md">ZwQueryInformationEnlistment</a>



<a href="..\wdm\ne-wdm-_enlistment_information_class.md">ENLISTMENT_INFORMATION_CLASS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ENLISTMENT_BASIC_INFORMATION structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

