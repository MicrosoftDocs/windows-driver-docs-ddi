---
UID: NS:ntddk._WHEA_IPF_CPE_DESCRIPTOR
title: _WHEA_IPF_CPE_DESCRIPTOR
author: windows-driver-content
description: The WHEA_IPF_CPE_DESCRIPTOR structure describes a corrected platform error (CPE) error source for an Itanium processor.
old-location: whea\whea_ipf_cpe_descriptor.htm
old-project: whea
ms.assetid: ffe1c550-a7cc-4d27-9a1e-287fdc7e08eb
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PWHEA_IPF_CPE_DESCRIPTOR, WHEA_IPF_CPE_DESCRIPTOR, whea.whea_ipf_cpe_descriptor, ntddk/PWHEA_IPF_CPE_DESCRIPTOR, _WHEA_IPF_CPE_DESCRIPTOR, *PWHEA_IPF_CPE_DESCRIPTOR, whearef_b64c919f-4854-4506-b14a-ec31b0a3e67e.xml, WHEA_IPF_CPE_DESCRIPTOR structure [WHEA Drivers and Applications], PWHEA_IPF_CPE_DESCRIPTOR structure pointer [WHEA Drivers and Applications], ntddk/WHEA_IPF_CPE_DESCRIPTOR
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
-	WHEA_IPF_CPE_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: WHEA_IPF_CPE_DESCRIPTOR, *PWHEA_IPF_CPE_DESCRIPTOR
---

# _WHEA_IPF_CPE_DESCRIPTOR structure


## -description


The WHEA_IPF_CPE_DESCRIPTOR structure describes a corrected platform error (CPE) error source for an Itanium processor.


## -syntax


````
typedef struct _WHEA_IPF_CPE_DESCRIPTOR {
  USHORT Type;
  UCHAR  Enabled;
  UCHAR  Reserved;
} WHEA_IPF_CPE_DESCRIPTOR, *PWHEA_IPF_CPE_DESCRIPTOR;
````


## -struct-fields




### -field Type

The type of error source descriptor. This member is always set to WHEA_ERROR_SOURCE_DESCRIPTOR_TYPE_IPFCPE.


### -field Enabled

A Boolean value that indicates if the error source is enabled.


### -field Reserved

Reserved for system use.


## -remarks


A WHEA_IPF_CPE_DESCRIPTOR structure is contained within the <a href="..\ntddk\ns-ntddk-_whea_error_source_descriptor.md">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure.



## -see-also

<a href="..\ntddk\ns-ntddk-_whea_error_source_descriptor.md">WHEA_ERROR_SOURCE_DESCRIPTOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_IPF_CPE_DESCRIPTOR structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

