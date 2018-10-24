---
UID: NF:hidpi.HidP_MaxDataListLength
title: HidP_MaxDataListLength function
author: windows-driver-content
description: The HidP_MaxDataListLength routine returns the maximum number of HIDP_DATA structures that HidP_GetData can return for a specified type of HID report and a specified top-level collection.
old-location: hid\hidp_maxdatalistlength.htm
tech.root: hid
ms.assetid: 525a44a5-4271-4079-917e-48eb679cb96d
ms.date: 04/30/2018
ms.keywords: HidP_MaxDataListLength, HidP_MaxDataListLength routine [Human Input Devices], hid.hidp_maxdatalistlength, hidfunc_2c103c6f-6177-47b3-9d52-9e15c97d758d.xml, hidpi/HidP_MaxDataListLength
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Hidparse.lib
-	Hidparse.dll
api_name:
-	HidP_MaxDataListLength
product:
- Windows
targetos: Windows
req.typenames: 
---

# HidP_MaxDataListLength function


## -description


The <b>HidP_MaxDataListLength</b> routine returns the maximum number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff539699">HIDP_DATA</a> structures that <a href="https://msdn.microsoft.com/library/windows/hardware/ff539718">HidP_GetData</a> can return for a specified type of HID report and a specified <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>.


## -parameters




### -param ReportType [in]

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539774">HIDP_REPORT_TYPE</a> enumerator value that indicates the report type.


### -param PreparsedData [in]

Pointer to a top-level collection's <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a>.


## -returns



If successful, <b>HidP_MaxDataListLength</b> returns the maximum number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff539699">HIDP_DATA</a> structures that <a href="https://msdn.microsoft.com/library/windows/hardware/ff539718">HidP_GetData</a> might return for a specified type of HID report and a specified <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>. Otherwise, the routine returns zero, which indicates that either the report type or the preparsed data is not valid.




## -remarks



User-mode applications or kernel-mode drivers call <b>HidP_MaxDataListLength</b> to determine the maximum number of  <a href="https://msdn.microsoft.com/library/windows/hardware/ff539699">HIDP_DATA</a> structures that <b>HidP_GetData</b> can return.

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539699">HIDP_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539718">HidP_GetData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539783">HidP_SetData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539679">_HIDP_PREPARSED_DATA</a>
 

 

