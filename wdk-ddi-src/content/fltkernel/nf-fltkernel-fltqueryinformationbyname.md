---
UID: NF:fltkernel.FltQueryInformationByName
title: FltQueryInformationByName function
author: windows-driver-content
description: The FltQueryInformationByName routine returns the requested information about a named file.
tech.root: ifsk
ms.assetid: dac542b8-eaea-4065-ae36-1433a6589ac3
ms.author: windowsdriverdev
ms.date: 09/14/2018
ms.topic: function
ms.keywords: FltQueryInformationByName
req.header: fltkernel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	DllExport
api_location: 
-	fltmgr.sys
api_name: 
-	FltQueryInformationByName
product:
-	Windows
targetos: Windows

---

# FltQueryInformationByName function


## -description

The **FltQueryInformationByName** routine returns the requested information about a named file.

## -parameters

### -param Filter

Specifies the filter that is initiating this operation.

### -param Instance

Specifies the instance towards which the create is targeted.

> [!IMPORTANT]
> *Instance* is not necessarily the initiating instance. It must match the instance towards which the create is targeted, if this parameter is non-**NULL**. If *Instance* is non-**NULL**, the current filter's pre-create callback is not called. The pre-callbacks start with the filter below the current filter.

### -param ObjectAttributes

Specifies the attributes to be used for the file object (for example, its name, SECURITY_DESCRIPTOR, etc.).

### -param IoStatusBlock

The address of the caller's I/O status block.

### -param FileInformation

A buffer to receive the requested information returned about the file.

### -param Length

The length, in bytes, of the *FileInformation* buffer.

### -param FileInformationClass

Specifies the type of information that should be returned about the file.

### -param DriverContext

A pointer to the driver's context space.

## -returns

Returns STATUS_SUCCESS if the operation is successful. Otherwise, returns an appropriate NTSTATUS error code.

## -remarks

This function returns requested information about a file without opening the actual file. The information returned is determined by the *FileInformationClass* that is specified, and it is placed into the caller's *FileInformation* buffer.

If *Instance* is non-**NULL** then the create will be targeted to the specified instance, calling all filters below the current filter before     sending the I/O down. If *Instance* is **NULL**, the I/O will be always sent to the top of the filter stack.

## -see-also