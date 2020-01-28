---
UID: NS:sti._ERROR_INFOW
title: _ERROR_INFOW (sti.h)
description: The STI_ERROR_INFO structure is used as a parameter for the IStiDevice::GetLastErrorInfo and IStiUSD::GetLastErrorInfo methods. It is also used as a member of the STI_DIAG structure.
old-location: image\sti_error_info.htm
tech.root: image
ms.assetid: e448ddfc-ae5a-4eb8-a39c-e46771278081
ms.date: 05/03/2018
ms.keywords: "*PSTI_ERROR_INFO, *PSTI_ERROR_INFOW, PSTI_ERROR_INFO, PSTI_ERROR_INFO structure pointer [Imaging Devices], STI_ERROR_INFO, STI_ERROR_INFO structure [Imaging Devices], STI_ERROR_INFOW, _ERROR_INFOW, image.sti_error_info, sti/PSTI_ERROR_INFO, sti/STI_ERROR_INFO, stifnc_c4e51568-9e80-4866-9258-72a8fcbd242d.xml"
f1_keywords:
 - "sti/STI_ERROR_INFO"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- sti.h
api_name:
- STI_ERROR_INFO
product:
- Windows
targetos: Windows
req.typenames: STI_ERROR_INFOW, *PSTI_ERROR_INFOW
---

# _ERROR_INFOW structure


## -description


The STI_ERROR_INFO structure is used as a parameter for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-getlasterrorinfo">IStiDevice::GetLastErrorInfo</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istiusd-getlasterrorinfo">IStiUSD::GetLastErrorInfo</a> methods. It is also used as a member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sti/ns-sti-_sti_diag">STI_DIAG</a> structure.


## -struct-fields




### -field dwSize

Caller-supplied size, in bytes, of the STI_ERROR_INFO structure.


### -field dwGenericError

Win32 error code.


### -field dwVendorError

Optional, vendor-specific error code.


### -field szExtendedErrorText

Optional character array containing a text string describing the error.

