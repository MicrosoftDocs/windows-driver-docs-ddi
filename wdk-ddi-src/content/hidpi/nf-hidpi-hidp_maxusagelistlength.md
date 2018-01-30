---
UID: NF:hidpi.HidP_MaxUsageListLength
title: HidP_MaxUsageListLength function
author: windows-driver-content
description: The HidP_MaxUsageListLength routine returns the maximum number of HID usages that HidP_GetUsages can return for a specified type of HID report and a specified top-level collection.
old-location: hid\hidp_maxusagelistlength.htm
old-project: hid
ms.assetid: 90491024-f623-4528-8d37-4a6acb394473
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: hidfunc_a038fac0-7532-40e4-b083-e0dbe046ad85.xml, HidP_MaxUsageListLength routine [Human Input Devices], hid.hidp_maxusagelistlength, HidP_MaxUsageListLength, hidpi/HidP_MaxUsageListLength
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hidpi.h
req.include-header: Hidpi.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
req.lib: Hidparse.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Hidparse.lib
-	Hidparse.dll
apiname:
-	HidP_MaxUsageListLength
product: Windows
targetos: Windows
req.typenames: HIDP_REPORT_TYPE
---

# HidP_MaxUsageListLength function


## -description


The <b>HidP_MaxUsageListLength</b> routine returns the maximum number of <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">HID usages</a> that <a href="..\hidpi\nf-hidpi-hidp_getusages.md">HidP_GetUsages</a> can return for a specified type of HID report and a specified <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>.


## -syntax


````
ULONG __stdcall HidP_MaxUsageListLength(
  _In_ HIDP_REPORT_TYPE     ReportType,
  _In_ USAGE                UsagePage,
  _In_ PHIDP_PREPARSED_DATA PreparsedData
);
````


## -parameters




### -param ReportType [in]

Specifies a <a href="..\hidpi\ne-hidpi-_hidp_report_type.md">HIDP_REPORT_TYPE</a> enumerator value that indicates the report type.


### -param UsagePage [in]

Specifies a <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usage page</a> as a search criteria. If <i>UsagePage</i> is zero, the routine returns the number of all the buttons in the collection.


### -param PreparsedData [in]

Pointer to a top-level collection's <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a>.


## -returns


If successful, <b>HidP_MaxUsageListLength</b> returns the maximum number of <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">HID usages</a> that <a href="..\hidpi\nf-hidpi-hidp_getusages.md">HidP_GetUsages</a> can return for a specified type of HID report and a specified <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>. If the specified preparsed data or report type is not valid, the routine returns zero.



## -remarks


For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539708">HidP_GetButtons</a>

<a href="..\hidpi\nf-hidpi-hidp_getusages.md">HidP_GetUsages</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff539679">_HIDP_PREPARSED_DATA</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidP_MaxUsageListLength routine%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

