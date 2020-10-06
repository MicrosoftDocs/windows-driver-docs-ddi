---
UID: NF:iddcx.IddCxReportCriticalError
title: IddCxReportCriticalError
tech.root: display
ms.date: 9/24/2020
ms.assetid: 05e99a48-390b-48db-8e4c-d60f4c1c7a0f
ms.topic: language-reference
targetos: Windows
description: IddCxReportCriticalError is an OS callback function called by an indirect display driver (IDD) to report a critical error.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: iddcx.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - iddcx.h
api_name:
 - IddCxReportCriticalError
f1_keywords:
 - IddCxReportCriticalError
 - iddcx/IddCxReportCriticalError
dev_langs:
 - c++
---

## -description

**IddCxReportCriticalError** is an OS callback function called by an indirect display driver (IDD) to report a critical error.

## -parameters

### -param AdapterObject

An [IDDCX_ADAPTER](/windows-hardware/drivers/display/iddcx-objects) object of the adapter on which the critical error occurred. If the error occurred before an IDDCX_ADAPTER was created, the IDD should pass ```nullptr```.

### -param pInArgs

Pointer to an [**IDARG_IN_REPORTCRITICALERROR**](ns-iddcx-idarg_in_reportcriticalerror.md) structure containing the error code of the critical error.

## -returns

If the routine succeeds it never returns to the driver because the driver process will be terminated.

## -remarks

When an IDD calls **IddCxCriticalError**, the OS will do the following:

* Bugcheck the driver with the following bugcheck code: ```(pInArgs->MajorErrorCode+0x100 << 8) + pInArgs->MinorErrorCode```. It is recommended that the driver use a unique combination of a major code and minor code so these cases can be identified in crashes and Watson reports.
* Terminate the driver process and restart according to the UMDF driver restart policy.
* If the caller is a remote IDD, disconnect the user session.

As a user mode memory dump is generated, the driver should place any useful debug information on the stack of the function that called **IddCxCriticalError**.

## -see-also

[**IDARG_IN_REPORTCRITICALERROR**](ns-iddcx-idarg_in_reportcriticalerror.md)
