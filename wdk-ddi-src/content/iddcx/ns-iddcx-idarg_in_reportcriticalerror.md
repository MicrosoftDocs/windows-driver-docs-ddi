---
UID: NS:iddcx.IDARG_IN_REPORTCRITICALERROR
title: IDARG_IN_REPORTCRITICALERROR
ms.date: 08/09/2022
tech.root: display
targetos: Windows
description: The IDARG_IN_REPORTCRITICALERROR structure contains information about a critical error being reported by an indirect display driver (IDD).
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: iddcx.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_IN_REPORTCRITICALERROR
f1_keywords:
 - IDARG_IN_REPORTCRITICALERROR
 - iddcx/IDARG_IN_REPORTCRITICALERROR
dev_langs:
 - c++
---

## -description

The **IDARG_IN_REPORTCRITICALERROR** structure contains information about a critical error being reported by an indirect display driver (IDD).

## -struct-fields

### -field MajorErrorCode

[In] The major error code for this critical error.  Valid range 0-0xff inclusive. IddCx will add 0x100 to this value before passing to Windows Error Reporting when creating a memory dump.

### -field MinorErrorCode

[in] The minor error code for this critical error.  Valid range 0-0xff inclusive.

## -remarks

It is recommended that the driver use a unique combination of a major code and minor code so these cases can be identified in crashes and Watson reports.

## -see-also

[**IddCxReportCriticalError**](nf-iddcx-iddcxreportcriticalerror.md)
