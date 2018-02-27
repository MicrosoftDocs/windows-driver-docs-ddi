---
UID: NF:sercx.SERCX_BUFFER_DESCRIPTOR_INIT
title: SERCX_BUFFER_DESCRIPTOR_INIT function
author: windows-driver-content
description: The SERCX_BUFFER_DESCRIPTOR_INIT function initializes a SERCX_BUFFER_DESCRIPTOR structure.
old-location: serports\sercx_buffer_descriptor_init.htm
old-project: serports
ms.assetid: 73C7C38A-F6E1-4276-A66A-0C16BC6E8F1C
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 1/SERCX_BUFFER_DESCRIPTOR_INIT, SERCX_BUFFER_DESCRIPTOR_INIT, SERCX_BUFFER_DESCRIPTOR_INIT function [Serial Ports], serports.sercx_buffer_descriptor_init
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: Any IRQL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	1.0\Sercx.h
api_name:
-	SERCX_BUFFER_DESCRIPTOR_INIT
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SERCX_BUFFER_DESCRIPTOR_INIT function


## -description


The <b>SERCX_BUFFER_DESCRIPTOR_INIT</b> function initializes a <a href="..\sercx\ns-sercx-sercx_buffer_descriptor.md">SERCX_BUFFER_DESCRIPTOR</a> structure.


## -syntax


````
VOID SERCX_BUFFER_DESCRIPTOR_INIT(
  _Out_ SERCX_BUFFER_DESCRIPTOR *Descriptor
);
````


## -parameters




### -param Descriptor [out]

A pointer to the <b>SERCX_BUFFER_DESCRIPTOR</b> structure that is to be initialized.


## -returns



None.




## -see-also

<a href="..\sercx\ns-sercx-sercx_buffer_descriptor.md">SERCX_BUFFER_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SERCX_BUFFER_DESCRIPTOR_INIT function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

