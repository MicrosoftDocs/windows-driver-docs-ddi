---
UID: NS:hidpi._USAGE_AND_PAGE
title: "_USAGE_AND_PAGE"
author: windows-driver-content
description: The USAGE_AND_PAGE structure specifies the usage page and usage ID of a HID control.
old-location: hid\usage_and_page.htm
tech.root: hid
ms.assetid: 48716117-c539-4436-a81f-4b05c9a8cb7d
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PUSAGE_AND_PAGE, PUSAGE_AND_PAGE, PUSAGE_AND_PAGE structure pointer [Human Input Devices], USAGE_AND_PAGE, USAGE_AND_PAGE structure [Human Input Devices], _USAGE_AND_PAGE, hid.usage_and_page, hidpi/PUSAGE_AND_PAGE, hidpi/USAGE_AND_PAGE, hidstrct_cbb3e4f3-5409-406c-9114-d8455e505497.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hidpi.h
req.include-header: Hidpi.h
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
-	hidpi.h
api_name:
-	USAGE_AND_PAGE
product:
- Windows
targetos: Windows
req.typenames: USAGE_AND_PAGE, *PUSAGE_AND_PAGE
---

# _USAGE_AND_PAGE structure


## -description


The USAGE_AND_PAGE structure specifies the <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usage page</a> and <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usage ID</a> of a HID control.


## -struct-fields




### -field UsagePage

Specifies a usage page.


### -field Usage

Specifies a usage ID within the usage page specified by <b>UsagePage</b>.


## -remarks



The<b> HidP_IsSameUsageAndPage</b> macro determines if two <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">extended usages</a>, represented by <b>USAGE_AND_PAGE</b> structures, are equal.


<pre class="syntax">BOOLEAN HidP_IsSameUsageAndPage(
   USAGE_AND_PAGE u1,
   USAGE_AND_PAGE u2
);
</pre>


<i>u1</i>

<b>USAGE_AND_PAGE</b>

Specifies an extended usage

<i>u2</i>

<b>USAGE_AND_PAGE</b>

Specifies an extended usage

<b>Return Value</b>

<b>BOOLEAN</b>

<b>HidP_IsSameUsageAndPage</b> returns one of the following status values:

<b>TRUE</b>

Usage <i>u1</i> is the same as usage <i>u2</i>.

<b>FALSE</b>

Usage <i>u1</i> is different than usage <i>u2</i>.

As defined by the USB HID standard, an extended usage is a 32-bit unsigned value. The high-order 16 bits specify the <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usage page</a>, and lower-order 16 bits specify the <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usage ID</a>.

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539712">HidP_GetButtonsEx</a>
 

 

