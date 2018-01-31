---
UID: NS:ntddk._WHEA_XPF_NMI_DESCRIPTOR
title: "_WHEA_XPF_NMI_DESCRIPTOR"
author: windows-driver-content
description: The WHEA_XPF_NMI_DESCRIPTOR structure describes a nonmaskable interrupt (NMI) error source for an x86 or x64 processor.
old-location: whea\whea_xpf_nmi_descriptor.htm
old-project: whea
ms.assetid: 4ffacbd6-dcdf-48a2-bf1e-6923d825bb09
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: WHEA_XPF_NMI_DESCRIPTOR, PWHEA_XPF_NMI_DESCRIPTOR structure pointer [WHEA Drivers and Applications], *PWHEA_XPF_NMI_DESCRIPTOR, ntddk/WHEA_XPF_NMI_DESCRIPTOR, WHEA_XPF_NMI_DESCRIPTOR structure [WHEA Drivers and Applications], _WHEA_XPF_NMI_DESCRIPTOR, PWHEA_XPF_NMI_DESCRIPTOR, whearef_47fae29e-d302-4028-961c-358ac647c0cc.xml, ntddk/PWHEA_XPF_NMI_DESCRIPTOR, whea.whea_xpf_nmi_descriptor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
-	ntddk.h
apiname:
-	WHEA_XPF_NMI_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: "*PWHEA_XPF_NMI_DESCRIPTOR, WHEA_XPF_NMI_DESCRIPTOR"
---

# _WHEA_XPF_NMI_DESCRIPTOR structure


## -description


The WHEA_XPF_NMI_DESCRIPTOR structure describes a nonmaskable interrupt (NMI) error source for an x86 or x64 processor.


## -syntax


````
typedef struct _WHEA_XPF_NMI_DESCRIPTOR {
  USHORT  Type;
  BOOLEAN Enabled;
} WHEA_XPF_NMI_DESCRIPTOR, *PWHEA_XPF_NMI_DESCRIPTOR;
````


## -struct-fields




#### - Type

The type of error source descriptor. This member is always set to WHEA_ERROR_SOURCE_DESCRIPTOR_TYPE_XPFNMI.


#### - Enabled

A Boolean value that indicates if the error source is enabled.


## -remarks


A WHEA_XPF_NMI_DESCRIPTOR structure is contained within the <a href="..\ntddk\ns-ntddk-_whea_error_source_descriptor.md">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure.



## -see-also

<a href="..\ntddk\ns-ntddk-_whea_error_source_descriptor.md">WHEA_ERROR_SOURCE_DESCRIPTOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_XPF_NMI_DESCRIPTOR structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

