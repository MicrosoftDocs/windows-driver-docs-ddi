---
UID: NS:sti._STI_DIAG
title: "_STI_DIAG" (sti.h)
description: The STI_DIAG structure is used as a parameter to the IStiDevice::Diagnostic and IStiUSD::Diagnostic methods.
old-location: image\sti_diag.htm
tech.root: image
ms.assetid: 07caa8b0-849c-4ad9-9adb-b1726edc9234
ms.date: 05/03/2018
ms.keywords: "*LPSTI_DIAG, DIAG, LPSTI_DIAG, LPSTI_DIAG structure pointer [Imaging Devices], STI_DIAG, STI_DIAG structure [Imaging Devices], _STI_DIAG, image.sti_diag, sti/LPSTI_DIAG, sti/STI_DIAG, stifnc_793c0930-51bf-46b5-89c9-9ddaf91a1fee.xml"
ms.topic: struct
req.header: sti.h
req.include-header: Sti.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	sti.h
api_name:
-	STI_DIAG
product:
- Windows
targetos: Windows
req.typenames: STI_DIAG, *LPSTI_DIAG
---

# _STI_DIAG structure


## -description


The STI_DIAG structure is used as a parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543736">IStiDevice::Diagnostic</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff543814">IStiUSD::Diagnostic</a> methods.


## -struct-fields




### -field dwSize

Caller-supplied size, in bytes, of the STI_DIAG structure.


### -field dwBasicDiagCode

Bit flag indicating the type of test to be performed. Currently this must be STI_DIAGCODE_HWPRESENCE<i>.</i>


### -field dwVendorDiagCode

Optional, vendor-defined diagnostic request code.


### -field dwStatusMask

Reserved for future use.


### -field sErrorInfo

Structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff548396">STI_ERROR_INFO</a>.

