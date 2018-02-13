---
UID: NF:ntddk.IoIsValidIrpStatus
title: IoIsValidIrpStatus function
author: windows-driver-content
description: The IoIsValidIrpStatus routine validates the specified NTSTATUS status code value.
old-location: kernel\ioisvalidirpstatus.htm
old-project: kernel
ms.assetid: 0A995357-A578-41C6-A1B8-ABD251C16C83
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoIsValidIrpStatus, IoIsValidIrpStatus routine [Kernel-Mode Driver Architecture], ntddk/IoIsValidIrpStatus, kernel.ioisvalidirpstatus
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoIsValidIrpStatus
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---

# IoIsValidIrpStatus function


## -description


The <b>IoIsValidIrpStatus</b> routine validates the specified NTSTATUS status code value.


## -syntax


````
LOGICAL IoIsValidIrpStatus(
  _In_ NTSTATUS Status
);
````


## -parameters




### -param Status [in]

The status code to be validated.


## -returns



<b>IoIsValidIrpStatus</b> returns <b>TRUE</b> if the <i>Status</i> parameter is a well-formed NTSTATUS value. Otherwise, the routine returns <b>FALSE</b>.




## -remarks



Driver developers can define custom NTSTATUS values for use as status codes for <a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a> requests. Drivers can call <b>IoIsValidIrpStatus</b> to validate the status codes for these requests. This routine is useful for detecting an uninitialized or corrupted <b>Status</b> value in the <a href="https://msdn.microsoft.com/59147bd1-6cd7-4fbe-b7bc-52e09ab88576">I/O status block</a> of an IRP.

<b>IoIsValidIrpStatus</b> detects invalid status codes that obviously violate the rules for defining custom NTSTATUS values, but might not detect invalid status codes that appear to follow the rules. The routine might return <b>TRUE</b> for a <i>Status</i> parameter that is not a valid NTSTATUS code value, but rarely, if ever, returns <b>FALSE</b> for a valid NTSTATUS code.

<b>IoIsValidIrpStatus</b> examines the <b>Sev</b>, <b>Facility</b>, and <b>Code</b> fields in the <i>Status</i> parameter value to determine whether the combination of values in these fields conforms to the published guidelines. If the <b>C</b> bit of the <i>Status</i> parameter is set, <b>IoIsValidIrpStatus</b> returns <b>TRUE</b> regardless of the other field values in <i>Status</i>.

For more information about these fields, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543026">Defining New NTSTATUS Values</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoIsValidIrpStatus routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

