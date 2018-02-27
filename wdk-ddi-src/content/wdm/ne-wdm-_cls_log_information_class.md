---
UID: NE:wdm._CLS_LOG_INFORMATION_CLASS
title: "_CLS_LOG_INFORMATION_CLASS"
author: windows-driver-content
description: The CLFS_LOG_INFORMATION_CLASS enumeration indicates the type of information that is requested by a call to ClfsQueryLogFileInformation.
old-location: kernel\clfs_log_information_class.htm
old-project: kernel
ms.assetid: afffe6c3-a6d1-4e43-ba2b-f64269c44ec0
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PCLFS_LOG_INFORMATION_CLASS, *PCLS_LOG_INFORMATION_CLASS, CLFS_LOG_INFORMATION_CLASS, CLFS_LOG_INFORMATION_CLASS enumeration [Kernel-Mode Driver Architecture], CLS_LOG_INFORMATION_CLASS, CLS_LOG_INFORMATION_CLASS enumeration [Kernel-Mode Driver Architecture], ClfsLogBasicInformation, ClfsLogBasicInformationPhysical, ClfsLogPhysicalLsnInformation, ClfsLogPhysicalNameInformation, ClfsLogStreamIdentifierInformation, ClfsLogSystemMarkingInformation, PCLFS_LOG_INFORMATION_CLASS, PCLFS_LOG_INFORMATION_CLASS enumeration pointer [Kernel-Mode Driver Architecture], PCLS_LOG_INFORMATION_CLASS, PCLS_LOG_INFORMATION_CLASS enumeration pointer [Kernel-Mode Driver Architecture], PPCLFS_LOG_INFORMATION_CLASS, PPCLFS_LOG_INFORMATION_CLASS enumeration pointer [Kernel-Mode Driver Architecture], PPCLS_LOG_INFORMATION_CLASS, PPCLS_LOG_INFORMATION_CLASS enumeration pointer [Kernel-Mode Driver Architecture], _CLS_LOG_INFORMATION_CLASS, kernel.clfs_log_information_class, sysenum_b63b4055-ea69-4955-8684-b42b148a3b7c.xml, wdm/CLFS_LOG_INFORMATION_CLASS, wdm/CLS_LOG_INFORMATION_CLASS, wdm/ClfsLogBasicInformation, wdm/ClfsLogBasicInformationPhysical, wdm/ClfsLogPhysicalLsnInformation, wdm/ClfsLogPhysicalNameInformation, wdm/ClfsLogStreamIdentifierInformation, wdm/ClfsLogSystemMarkingInformation, wdm/PCLFS_LOG_INFORMATION_CLASS, wdm/PCLS_LOG_INFORMATION_CLASS, wdm/PPCLFS_LOG_INFORMATION_CLASS, wdm/PPCLS_LOG_INFORMATION_CLASS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
-	Wdm.h
apiname:
-	CLS_LOG_INFORMATION_CLASS
product: Windows
targetos: Windows
req.typenames: CLS_LOG_INFORMATION_CLASS, *PCLS_LOG_INFORMATION_CLASS, PPCLS_LOG_INFORMATION_CLASS
req.product: Windows 10 or later.
---

# _CLS_LOG_INFORMATION_CLASS enumeration


## -description


The <b>CLFS_LOG_INFORMATION_CLASS</b> enumeration indicates the type of information that is requested by a call to <a href="..\wdm\nf-wdm-clfsquerylogfileinformation.md">ClfsQueryLogFileInformation</a>.


## -syntax


````
typedef enum _CLS_LOG_INFORMATION_CLASS { 
  ClfsLogBasicInformation             = 0,
  ClfsLogBasicInformationPhysical     = 1,
  ClfsLogPhysicalNameInformation      = 2,
  ClfsLogStreamIdentifierInformation  = 3,
  ClfsLogSystemMarkingInformation     = 4,
  ClfsLogPhysicalLsnInformation       = 5
} CLS_LOG_INFORMATION_CLASS, *PCLS_LOG_INFORMATION_CLASS, **PPCLS_LOG_INFORMATION_CLASS, CLFS_LOG_INFORMATION_CLASS, *PCLFS_LOG_INFORMATION_CLASS, **PPCLFS_LOG_INFORMATION_CLASS;
````


## -enum-fields




### -field ClfsLogBasicInformation

Indicates that the request is for basic information about a CLFS stream and its underlying physical log. The information is returned in a <a href="..\wdm\ns-wdm-_cls_information.md">CLFS_INFORMATION</a> structure. Most of the structure members contain information about the underlying physical log, but some members contain information that is specific to the stream.


### -field ClfsLogBasicInformationPhysical

Indicates that the request is for basic information about the physical log that underlies a CLFS stream. The information is returned in a <b>CLFS_INFORMATION</b> structure. All of the structure members contain information about the underlying physical log.


### -field ClfsLogPhysicalNameInformation

Indicates that the request is for information about the name of a physical CLFS log. The information is returned in a <b>CLFS_LOG_NAME_INFORMATION</b> structure.


### -field ClfsLogStreamIdentifierInformation

Indicates that the request is for a CLFS stream identifier. The information is returned in a <a href="..\wdm\ns-wdm-_clfs_stream_id_information.md">CLFS_STREAM_ID_INFORMATION</a> structure.


### -field ClfsLogSystemMarkingInformation

Count of system marking references. This enumeration constant is supported only in Windows Vista and later versions of Windows.


### -field ClfsLogPhysicalLsnInformation

Maps virtual LSNs to physical LSNs; only valid for physical logs. This enumeration constant is supported only in Windows Vista and later versions of Windows.


## -remarks



The <i>eInformationClass</i> parameter of the <a href="..\wdm\nf-wdm-clfsquerylogfileinformation.md">ClfsQueryLogFileInformation</a> function is a value from the <b>CLFS_LOG_INFORMATION_CLASS</b> enumeration.




## -see-also

<a href="..\wdm\nf-wdm-clfsquerylogfileinformation.md">ClfsQueryLogFileInformation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20CLS_LOG_INFORMATION_CLASS enumeration%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

