---
UID: NS:sti._ERROR_INFOW
title: "_ERROR_INFOW"
author: windows-driver-content
description: The STI_ERROR_INFO structure is used as a parameter for the IStiDevice::GetLastErrorInfo and IStiUSD::GetLastErrorInfo methods. It is also used as a member of the STI_DIAG structure.
old-location: image\sti_error_info.htm
old-project: image
ms.assetid: e448ddfc-ae5a-4eb8-a39c-e46771278081
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "_ERROR_INFOW, STI_ERROR_INFO, STI_ERROR_INFOW, *PSTI_ERROR_INFOW, PSTI_ERROR_INFO structure pointer [Imaging Devices], sti/PSTI_ERROR_INFO, *PSTI_ERROR_INFO, image.sti_error_info, stifnc_c4e51568-9e80-4866-9258-72a8fcbd242d.xml, PSTI_ERROR_INFO, sti/STI_ERROR_INFO, STI_ERROR_INFO structure [Imaging Devices]"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	sti.h
apiname:
-	STI_ERROR_INFO
product: Windows
targetos: Windows
req.typenames: "*PSTI_ERROR_INFOW, STI_ERROR_INFOW"
req.product: Windows 10 or later.
---

# _ERROR_INFOW structure


## -description


The STI_ERROR_INFO structure is used as a parameter for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543749">IStiDevice::GetLastErrorInfo</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff543820">IStiUSD::GetLastErrorInfo</a> methods. It is also used as a member of the <a href="..\sti\ns-sti-_sti_diag.md">STI_DIAG</a> structure.


## -syntax


````
typedef struct _ERROR_INFO {
  DWORD dwSize;
  DWORD dwGenericError;
  DWORD dwVendorError;
  WCHAR szExtendedErrorText[255];
} STI_ERROR_INFO, *PSTI_ERROR_INFO;
````


## -struct-fields




#### - dwSize

Caller-supplied size, in bytes, of the STI_ERROR_INFO structure.


#### - dwGenericError

Win32 error code.


#### - dwVendorError

Optional, vendor-specific error code.


#### - szExtendedErrorText

Optional character array containing a text string describing the error.

